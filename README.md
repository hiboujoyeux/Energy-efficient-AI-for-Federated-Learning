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

Le dossier `GRASP` contient le notebook à exécuter pour évaluer la méthode Federated GraSP (FedGraSP) sur le dataset MNIST

Structure des notebooks pour la quantification


1️ Import des bibliothèques

Chargement des dépendances nécessaires à l’exécution :

Pytorch, Numpy, IO...

2️ Distribution des données (Dirichlet)

Application d’un échantillonnage de type Dirichlet pour simuler un environnement IID ou non-IID :

Répartition des données entre clients
Contrôle de l’hétérogénéité des labels

3️ Quantification / Déquantification

Implémentation des fonctions de :

quantification (FP16 / INT8 / INT4)
déquantification

Ces fonctions permettent de :

compresser les poids
réduire la communication entre clients et serveur

4️ Federated Learning

Mise en place de l’algorithme de Federated Learning :

Envoi du modèle global aux clients
Entraînement local
Agrégation des modèles (type FedAvg ou FedProx)
Mise à jour du modèle global

5️ Métriques et visualisation

Calcul et stockage des métriques :

loss
accuracy
temps par round
taille du modèle

Génération de graphiques pour analyser :

la loss
l'accuracy
l’impact de la quantification

6️ Exécution

Lancement complet de l’expérience avec :

metrics = federated_learning_loop(run_save_dir)

Résultats obtenus :

performances du modèle
évolution des métriques
modèles sauvegardés

 Résultats

Les résultats incluent :

 Courbes de loss et accuracy
⏱ Temps d’entraînement par round

 Remarques
Chaque méthode de quantification est testée indépendamment
Les notebooks peuvent être exécutés séparément pour comparer les approches
