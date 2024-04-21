# A BERT-based pretraining model for extracting molecular structural information from a SMILES sequence

'datasetMake_pretrain.ipynb' is used to prepare input and target data for pretraining, it also creat a file for saving the dictionary of symbols.
'pretrain.ipynb' is used to conduct pre-training experiment.
'PropertyPred.ipynb' is used to conduct experiment of molecular properties.

Remember to change all file path to the path in your system.

The version of Pytorch used in this work is 1.11.0. The version of RDKit used in this work is 2021.09.4

The datasets used for molecular properties prediction is provided by Therapeutics Data Commons (TDC), we loaded datasets through TDC with default setting, an example of loading Caco-2 dataset is shown in bellow:
```
import tdc
tdc_group = tdc.benchmark_group.admet_group(path = 'my_file_path/')
benchmark = tdc_group.get('Caco2_Wang')
train_val, test_set = benchmark['train_val'], benchmark['test']
train_set, valid_set = tdc_group.get_train_valid_split(benchmark ='Caco2_Wang', split_type = 'default', seed =_seed) # _seed is set to 0,1,2,3,4
```