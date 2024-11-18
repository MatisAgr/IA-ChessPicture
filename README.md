# Reconnaissance de Pions d'Échecs avec IA

Ce projet utilise des images pour entraîner des modèles d'intelligence artificielle capables de reconnaître différents pions d'échecs (roi, reine, cavalier, etc.). Le projet exploite deux types de modèles : un **Perceptron Multicouche (MLP)** et un **Arbre de Décision**.

### Version PyTorch
Une version de ce projet est également disponible en utilisant PyTorch pour une meilleure précision, efficacité et des paramètres optimisés pour les modèles CNN.

## Structure du Projet

- `ChessDataset/Train/` : Répertoire contenant les images d'entraînement organisées par classe (par exemple : `Roi`, `Reine`, etc.).
- `ChessDataset/Test/` : Répertoire contenant les images de test organisées par classe.

*(Le nom des dossiers sert pour donner des noms aux )
## Prérequis

Avant d'exécuter le projet, assurez-vous d'installer les bibliothèques nécessaires avec la commande suivante :

```bash
pip install scikit-learn matplotlib pillow
```

# Étapes du Projet
1. Chargement des données : Les images sont chargées et prétraitées (redimensionnement à 150x150, conversion RGB, normalisation).
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

Rép: Roi
IA: Roi
[IMAGE]

# Visualisation de l'Arbre de Décision
L'arbre de décision est visualisé pour analyser les règles de classification apprises.

# Améliorations Futures
- Ajout de modèles plus avancés comme les réseaux de neurones convolutifs (CNN) pour une meilleure précision, car actuellement l'accuracy est assez faible.
- Ajout d'augmentation de données pour rendre le modèle plus robuste.
- Optimisation des hyperparamètres.