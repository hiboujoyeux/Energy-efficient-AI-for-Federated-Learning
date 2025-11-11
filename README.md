# Energy efficient AI for Federated Learning

Chaque dossier est un entraînement d'un modèle sur une base de données. Un dossier est composé de quatre fichiers (ici dans `fl_mnist_default`) :
- `fl_mnist_default.ipynb` : un notebook implémentant l'entraînement, ici sur MNIST et sans méthode de compression
- `checkpoints` : un dossier comportant des modèles à différentes étapes de l'entraînement
- `training_metrics.png` : un plot des métriques suivies lors de l'entraînement
- `summary.json` : un fichier json comportant des statistiques sur l'entraînement
