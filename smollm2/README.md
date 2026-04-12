# SmolLM2 135M Instruct - Fine tuning

Le dossier `smollm2` contient les notebooks pour le fine tuning et le benchmark de smollm2 :
- `SmolLM2_135M_Instruct_finetune` : tous les fichiers relatifs au fine tuning en fp32 + le modèle de base
- `SmolLM2_135M_Instruct_finetune_bf16` : tous les fichiers relatifs au fine tuning en bf16
- `SmolLM2_135M_Instruct_finetune_adaptative` : tous les fichiers relatifs au fine tuning avec la méthode adaptative, méthode mélangeant bf16 et fp32 pendant l'entraînement

Les notebooks `*.ipynb` sont les notebooks contenant le code pour le fine tuning de SmolLM2 135M Instruct.

Les fichiers `*.json` sont les résultats du benchmark pour chacun des modèles entraînés. `row1272` siginifie simplement que c'est le dernier checkpoint (comprenant l'entièreté de l'évaluation), le dataset du benchmark comportant 1273 lignes de données.