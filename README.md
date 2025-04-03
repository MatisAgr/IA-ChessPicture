# Reconnaissance de Pions d'Échecs avec IA
[![wakatime](https://wakatime.com/badge/user/a16f794f-b91d-4818-8dfc-d768ce605ece/project/6b23f3f1-42a9-468b-809a-3fa525befdf5.svg)](https://wakatime.com/badge/user/a16f794f-b91d-4818-8dfc-d768ce605ece/project/6b23f3f1-42a9-468b-809a-3fa525befdf5) + [![wakatime](https://wakatime.com/badge/user/a16f794f-b91d-4818-8dfc-d768ce605ece/project/fccc6583-d3b5-44d3-aa13-fc04318d316b.svg)](https://wakatime.com/badge/user/a16f794f-b91d-4818-8dfc-d768ce605ece/project/fccc6583-d3b5-44d3-aa13-fc04318d316b)

Ce projet utilise des images pour entraîner des modèles d'intelligence artificielle capables de reconnaître différents pions d'échecs (roi, reine, cavalier, etc.). Le projet exploite deux types de modèles : un **Perceptron Multicouche (MLP)** et un **Arbre de Décision**.
<br />Le but est que notre IA puisse reconnaitre les icones numérique des pions d'échec à l'aide des connaissances sur des images de pions du monde réel.

Exemple :
| Image Réelle (Train) | Icone numérique (Test) | Réponse attendue |
|:------------:|:---------------:|:----------------:|
|![00000002](https://github.com/user-attachments/assets/53f53189-4e3b-466c-b9fd-0295e02ddb64)|![96](https://github.com/user-attachments/assets/7cc8ad32-718e-4d63-8fa2-ae391d8a0a4c)|Tour




Possibilité de choisir pour le sklearn, la verison de traitement des images en couleur ou en nuance de gris.

### Version PyTorch
Une version de ce projet est également disponible en utilisant PyTorch pour une meilleure précision, efficacité et des paramètres optimisés pour les modèles CNN. De plus à l'aide de la librairie `transforms`, j'ai pu faire des manpulations sur les images tel que : 
- Rotation aléatoire
- Transformation affine
- Normalise les couleurs de l'image (RVB)
- Convertit l'image en tenseur (tableau multidimensionnel PyTorch) 

## Structure du Projet

- `ChessDataset/Train/` : Répertoire contenant les images d'entraînement organisées par classe (par exemple : `Roi`, `Reine`, etc.).
- `ChessDataset/Test/` : Répertoire contenant les images de test organisées par classe.

*(Le nom des dossiers sert pour donner des noms aux classes)

À savoir que les images de **Train** sont des images dans le **monde réel de vraies pieces en plus des dessins**, <br /> sachant que les images de **Test** sont des icones plus courrament utilisé dans le monde numérique.

## Prérequis

Avant d'exécuter le projet, assurez-vous d'installer les bibliothèques nécessaires avec la commande suivante :

```bash
pip install scikit-learn matplotlib pillow
```

# Étapes du Projet
1. Choisir le projet sklearn_grey / sklearn_color / torch
1. Chargement des données : Les images sont chargées et prétraitées (redimensionnement à 150x150, conversion RGB ou L, normalisation).
2. Entraînement :
    - Modèle MLP : Un perceptron multicouche est entraîné pour classifier les pions.
    - Modèle Arbre de Décision : Une alternative plus simple pour la classification.
3. Évaluation :
    - Précision et rapport de classification sur l'ensemble de validation.
    - Précision et rapport sur l'ensemble de test.
4. Visualisation : Affichage des prédictions pour un échantillon d'images.

# Exécution du Code
1. Charger et prétraiter les données :
    Le code charge les images depuis les répertoires et les redimensionne pour le traitement.
<br />

2. Entraîner le modèle :
    Le modèle MLPClassifier est utilisé avec :
    - 512, 256, 128 neurones par couche cachée.
    - Taux d'apprentissage : 0.0001
    - Optimisation : SGD

Vous pouvez également entraîner un Arbre de Décision comme alternative.
<br />

3. Évaluer le modèle :
Les précisions sont affichées pour les ensembles de validation et de test.
<br />

4. Afficher les résultats :

Des images de l'ensemble de test sont affichées avec leurs prédictions.

# Exemple d'Affichage des Prédictions
Le programme affiche un sous-ensemble d'images de test, avec les étiquettes réelles et prédites :

- Exemple :
![grey](https://github.com/user-attachments/assets/871932d9-ace8-46be-a1ec-aac8c620ea19)
![color](https://github.com/user-attachments/assets/8cda7f38-30b0-49ef-9737-ac18fb6f7492)


# Visualisation de l'Arbre de Décision
L'arbre de décision est visualisé pour analyser les règles de classification apprises :

![output](https://github.com/user-attachments/assets/2faa9000-6fee-4c1c-bd66-533bfbffb88e)


# Améliorations Futures
- Ajout d'augmentation de données pour rendre le modèle plus robuste.
- Optimisation des hyperparamètres.
