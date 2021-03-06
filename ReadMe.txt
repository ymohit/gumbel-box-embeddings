You are here - The top level of the code directory for Neurips2020 submission.

**Overview:

Folders:

data - Contains all the dataset used in this paper.

boxes - Contains implemntation of different types of box embeddings including our proposed models.
src/datasets - Contains the dataset pipeline to feed allenNLP

models/box/gumbel_bce_box.py - Contains the implementation of Tasks for GumbelBox.
models/box/bce_box.py - Contains the implementation of Tasks for SmoothBox and Gaussian.

configs - Contains ".jsonnet" files for each experiemnt that we report. These files contains the best hyperparameter for the corresponding task that file refers to.

**Install:

conda create -n neurips2020 python=3.6
source activate neurips2020
pip install allennlp==0.9.0
pip install typing_extensions
pip install networkx


**Run:

Note that config files corresponding to all the experiments are in "configs" folder. They are in ".jsonnet" format.

Run the following:
allennlp train configs/choose_you_config_file -s logs/Exp_you_want_to_run/ --include-package models --include-package datasets  -f

**Configs
For experiments (Section 5.3) with WordNet's full noun hierarchy the config files will be similar to the following:
wordnet_full_{model_name}_{with or without(wo)}_reg.jsonnet

For experiments (Section 5.1) on ranking task on different tree-structures:
{tree_name}_{model_name}_{number_of_dim}.jsonnet

With this information the confog names are self explanatory.

**Results
The value of different metrics for the experiment can be found in the log_directory/metrics.json.
