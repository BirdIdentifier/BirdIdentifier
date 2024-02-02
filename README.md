# BirdIdentifier 🐦

## Bonjour et bienvenue sur le dépôt du projet BirdIdentifier ! 👋

*******

Sommaire 
 1. [Accessibilité](#acces)
 2. [Présentation du projet](#presentation)
 3. [Notre jeu de données](#dataset)
 4. [Description des librairies](#libraries)
 5. [Avancement](#avancement)
 6. [Auteurs](#auteurs)

*******

<div id='acces'/>   

## Accessibilité ↗️

> **Warning**: Le déploiement n'a pas encore été fait. 

*******

<div id='dataset'/>  

## Notre jeu de données 📁

Notre jeu de données contient plus de **80000 images** de plus de **500 espèces d'oiseaux** différentes ! Parmi ces images, nous avons des images **d'entraînement**, de **test** et **d'imagination**. Il s'agit d'un jeu de données de très haute qualité, où chaque image ne contient qu'**un seul oiseau** occupant généralement **au moins 50 % des pixels** de l'image. En conséquence, même un modèle modérément complexe atteindra des précisions d'entraînement et de test dans la plage des **90 %**.  

Toutes les images sont au **format jpg** et ont une **taille de 224 x 224 x 3 pixels en couleur**. Le jeu de données inclut également un fichier **birds.csv**. Ce fichier CSV contient **5 colonnes** : 
- la colonne **filepaths** contient le chemin relatif du fichier image, 
- la colonne **labels** contient le nom de la classe d'espèce d'oiseau associée au fichier image, 
- la colonne **scientific label** contient le nom scientifique latin de l'image, 
- la colonne **data set** indique dans quel ensemble de données (entraînement, test ou validation) se trouve le chemin du fichier, 
- la colonne **class_id** contient la valeur d'index de classe associée à la classe du fichier image.  

*******

<div id='libraries'/>   

## Librairies utilisées 📚  

### **cv2**    

> OpenCV (Open Source Computer Vision) est une bibliothèque open-source spécialisée dans le traitement d'images et la vision par ordinateur. En Python, la version la plus couramment utilisée de cette bibliothèque est appelée **cv2**.    

***Fonctionnalités*** :   

*Traitement d'Images* : OpenCV offre un ensemble complet de fonctionnalités pour lire, écrire, manipuler et traiter des images.

*Détection d'Objets* : La bibliothèque propose des outils puissants pour la détection d'objets, y compris la reconnaissance faciale, la détection de contours et la correspondance des formes.

*Transformation et Filtrage* : OpenCV permet la transformation d'images, la convolution, le filtrage et d'autres opérations permettant de modifier l'apparence des images.

*Vision par Ordinateur* : Idéale pour le développement de projets de vision par ordinateur, OpenCV fournit des algorithmes pour le suivi d'objets, la stéréovision, la calibration de caméra, etc.

[Documentation Officielle](https://opencv.org/)

### **os.path**   

> Le module **os.path** fait partie du module **os** en Python et offre des fonctionnalités spécifiques pour la manipulation des chemins de fichiers et des noms de fichiers.  

***Fonctionnalités*** :   

*Manipulation de Chemins* : Le module os.path fournit des méthodes pour manipuler des chemins de fichiers de manière portable entre les systèmes d'exploitation, en prenant en compte les différences dans les séparateurs de répertoire (/ ou \) et les conventions spécifiques à chaque plateforme.

*Validation de Chemins* : Vous pouvez utiliser les fonctions du module pour vérifier l'existence de fichiers ou de répertoires, tester si un chemin est absolu ou relatif, et obtenir des informations sur les fichiers comme la taille ou la date de modification.

*Construction de Chemins* : Facilite la création de chemins de fichiers en combinant des répertoires et des noms de fichiers de manière sûre et portable.

[Documentation Officielle](https://docs.python.org/3/library/os.path.html)  

### **matplotlib.pyplot**  

> **matplotlib.pyplot** est un module de la bibliothèque Matplotlib, largement utilisée pour la création de graphiques et de visualisations en Python. Ce module spécifique fournit une interface similaire à celle de MATLAB, facilitant la création de graphiques de manière interactive.  

***Fonctionnalités*** :   

*Création de Graphiques* : Matplotlib permet de créer une variété de graphiques, y compris des tracés de lignes, des histogrammes, des diagrammes à barres, des diagrammes en boîte, etc.

*Personnalisation* : Vous pouvez personnaliser chaque aspect du graphique, y compris les étiquettes d'axe, les titres, les couleurs, les styles de ligne, et plus encore.

*Visualisation en Temps Réel* : Idéal pour l'exploration de données, le module pyplot facilite la création de graphiques interactifs pour visualiser des données en temps réel.

[Documentation Officielle](https://matplotlib.org/3.5.3/api/_as_gen/matplotlib.pyplot.html)  

### **sklearn**  

> **scikit-learn**, également connu sous le nom de **sklearn**, est une bibliothèque open-source en Python dédiée à l'apprentissage automatique (machine learning). Elle offre des outils simples et efficaces pour la classification, la régression, le clustering, la réduction de dimensionnalité, et bien plus encore.

***Fonctionnalités*** :   

*Large Gamme d'Algorithmes* : scikit-learn propose une variété d'algorithmes d'apprentissage automatique, allant des méthodes classiques aux techniques avancées, couvrant la plupart des besoins en modélisation.

*Facilité d'Utilisation* : La bibliothèque est conçue pour être conviviale, avec une API cohérente et une documentation détaillée, facilitant la prise en main même pour les débutants.

*Traitement de Données* : sklearn fournit des outils pour la préparation et la transformation des données, y compris la normalisation, la standardisation, le traitement des valeurs manquantes, et plus encore.

*Évaluation des Modèles* : Des fonctions d'évaluation de modèles telles que la validation croisée, les courbes ROC, et les métriques de performance facilitent l'évaluation des performances des modèles.

[Documentation Officielle](https://scikit-learn.org/stable/)

*******

<div id='presentation'/>

## **Présentation** 🎉

BirdIdentifier : Votre identificateur d'oiseaux à partir d'une photo !  

*******

<div id='avancement'/>   

## Avancement

### Analyse du système :

Pour commencer, nous avons d'abord décidé d'analyser notre système et le jeu de données que nous avons choisi.      

Nous avons donc eu pour chaque donnée : un **X** (la photo de l'oiseau) et un **Y** (le nom de son espèce).  
Pour traiter ces derniers, nous avons pour la photo (X) : redimensionner celle-ci puis normaliser les pixels. Ensuite, pour le nom de l'espèce (Y), nous avons fait le choix de lui attribuer un entier.  
Un autre détail important et que nous avons placer ceux deux ensembles de valeurs dans des tableaux de tailles identiques avec les valeurs correspondantes à la même position.  

### Nos modèles :

A présent, nous avons dû passer au choix de notre modèle, ou plutôt de nos modèles dans notre cas. En effet, nous avons fait le choix de tester **2 modèles différents** :  
- Un **arbre de décision** avec deux espèces
- Un **réseau de neuronnes (CNN)** avec toutes les espèces 

Le premier modèle aura pour but de nous familiariser avec l'environnement de travail et les différentes librairies vu ci-dessus avec l'aide d'un cas simple.  
Le second sera une réelle implémentation du modèle en utilisant l'intégralité et l'ensemble des possibilités de notre jeu de données.  

### Premier modèle - Arbre de décision :

Nous avons donc débuté à l'aide d'un **cas binaire** et donc les deux espèces suivantes : *Masked Booby & Crested Coua*.

> *Pseudo code d'entraînement du modèle :*  
>- Charger les données (photos des oiseaux)  
>- Placer les chemins des photos des oiseaux au sein d'un tableau
>- Récupérer les images de tests et les traiter :
>    - Redimensionnement
>    - Normalisation
>- Entraîner le modèle
>- Évaluer les performances sur l'ensemble de test

*******

<div id='auteurs'/>

## **Auteurs** 👥

Étudiant 3ème Annnée - BUT Informatique - IUT Clermont Auvergne - 2023-2024   
`BRODA Lou` - `FRANCO Nicolas`
