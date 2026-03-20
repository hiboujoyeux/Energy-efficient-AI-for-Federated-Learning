# Energy efficient AI for Federated Learning

Ce repo contient une étude des méthodes de compression appliqué au machine learning, notamment sur des réseaux de neurones multicouches simples et des réseaux de neurones résiduel dans le cadre de l'apprentissage fédéré, ainsi que sur du fine tuning de modèles de langage.

Chaque dossier précédé de `fl` est un entraînement d'un modèle sur une base de données. Un dossier est composé de quatre fichiers (ici dans `fl_mnist_default`) :
- `fl_mnist_default.ipynb` : un notebook implémentant l'entraînement, ici sur MNIST et sans méthode de compression
- `checkpoints` : un dossier comportant des modèles à différentes étapes de l'entraînement
- `training_metrics.png` : un plot des métriques suivies lors de l'entraînement
- `summary.json` : un fichier json comportant des statistiques sur l'entraînement

Le dossier `smollm2` contient les notebooks pour le fine tuning et le benchmark de smollm2 :
- `SmolLM2_135M_Instruct_finetune` : tous les fichiers relatifs au fine tuning en fp32 + le modèle de base
- `SmolLM2_135M_Instruct_finetune_bf16` : tous les fichiers relatifs au fine tuning en bf16
- `SmolLM2_135M_Instruct_finetune_adaptative` : tous les fichiers relatifs au fine tuning avec la méthode adaptative, méthode mélangeant bf16 et fp32 pendant l'entraînement
