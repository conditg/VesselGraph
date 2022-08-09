[![DOI](https://zenodo.org/badge/399400923.svg)](https://zenodo.org/badge/latestdoi/399400923)
![alt text](graph_abstract.png "Logo Title Text 1")
## Introduction
Welcome to the project page of *VesselGraph*  A Dataset and Benchmark for Graph Learning and Neuroscience. <br/>

Biological neural networks define human and mammalian brain function and intelligence and form ultra-large, spatial, structured graphs. Their neuronal organization is closely interconnected with the spatial organization of the brain's microvasculature, which supplies oxygen to the neurons and builds a complementary spatial graph. In this project we are providing an extendable dataset of whole-brain vessel graphs based on various multi-center imaging protocols. 

This new dataset paves a pathway towards translating advanced graph learning research into the field of neuroscience. Complementarily, the new dataset raises challenging graph learning research questions for the machine learning community, for example how to incorporate biological priors in a meaningful and interpretable way into learning algorithms. 


## Features
- *Whole brain vessel graphs:* are the key for research questions to Biology and Neuroscience, including Neuronal organisation, stroke modeling and hemodynamics
- *Ready-to use and large set of data:* We are providing whole brain graphs from different research groups and will continously update our dataset.
- *Data-Loaders:* We are providing extensive functions to readily process our data for machine learning research, including the community standard OGB and pyG dataloaders
- *Benchmarks:* We benchmarked a comprehensive set of state of the art methods in link prediction and node classification; we provide all codes and detailed instructions
- *Open-source, “living” initiative:* VesselGraph is an open source initiative. We want to expand our datasets as soon as other brain imaging becomes publicly available


![alt text](synthetic_overview.png "Logo Title Text 1")

## Cite us

- [arXiv link](https://arxiv.org/abs/2108.13233)
- [Published in NIPS 2021 Dataset & Benchmark Track](https://nips.cc/Conferences/2021/ScheduleMultitrack?event=29873)

```
@misc{paetzold2021brain,
      title={Whole Brain Vessel Graphs: A Dataset and Benchmark for Graph Learning and Neuroscience (VesselGraph)}, 
      author={Johannes C. Paetzold and Julian McGinnis and Suprosanna Shit and Ivan Ezhov and Paul Büschl and Chinmay Prabhakar and Mihail I. Todorov and Anjany Sekuboyina and Georgios Kaissis and Ali Ertürk and Stephan Günnemann and Bjoern H. Menze},
      year={2021},
      eprint={2108.13233},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```
Please cite this work if any of our code or datasets are helpful for your research. Considering the specific graphs and baseline models please also cite the respective original articles as described in the preprint.
## License 

Our software is licensed under the [MIT license](https://github.com/jocpae/VesselGraph/LICENSE).
The data is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Namensnennung-Nicht kommerziell 4.0 International Lizenz</a>.


## Quick Start

### Table of contents

* [Dataset Description](#dataset-description)
* [Dataloader Instruction](#dataloader-instruction)
* [Baseline Instruction](#baseline-instruction)

_NOTE: Currently, our graphs are not officially included in the OGB dataset yet. Please use our custom version of `ogb` in `./source/` instead of the official pip ogb package for now. (See Issue [#4](https://github.com/jocpae/VesselGraph/issues/4).)_

We provide our graphs as preprocessed OGB datasets (OGBN and OGBL) that are automatically retrieved by the dataloaders when executing the algorithms in `./source/baseline_models/`.

If you would rather work with customized solutions (different datasplits, etc.), we provide you with all steps of our pipeline to generate, preprocess and convert the raw graphs to PyG
and OGB formats. In the following section, we describe how our graphs have been built. You are invited to skip this section if you prefer working with our preprocessed graphs.

For this step, please run `./source/ogb_dataset/link_prediction/update_ogbl_master.sh` and `./source/ogb_dataset/node_classification/update_ogbn_master.sh` once after including your own dataset, so it will be broadcasted to the ogb dataloaders, before you execute any of the algorithms in `./source/baseline_models`.

### Dataset Description

This is the description about how we prepared the dataset. The parameters are described as used in the paper
#### 1. Generate Raw Graph fron Segmentation using Voreen
Use [Voreen Graph Generation Tool](https://github.com/jqmcginnis/voreen_tools) to make the `node_list` and `edge_list` from a segmentation volume.

#### 2. Preprocess Dataset

Go to [`./source/dataset_preprocessing/`](./source/dataset_preprocessing/) and run `process_edge_list.py` with arguments of `--node_list` and `--edge_list`

#### Download Dataset
|Dataset Name | Raw | Preprocessed |
|-----|-------------|--------------|
`BALBc_no1`|[download](https://syncandshare.lrz.de/getlink/fiWxG4k3jRhLNGmW7RHddvKY/BALBc_no1_raw.zip) |[download](https://syncandshare.lrz.de/dl/fiG21AiiCJE6mVRo6tUsNp4N/BALBc_no1.zip) |
`BALBc_no2` |[download](https://syncandshare.lrz.de/getlink/fiCWEj5mnuwDkgbjww6CAbF4/BALBc_no2_raw.zip) |[download](https://syncandshare.lrz.de/dl/fiS6KM5NvGKfLFrjiCzQh1X1/BALBc_no2.zip) |
`BALBc_no3` |[download](https://syncandshare.lrz.de/getlink/fiBNTpDbmMQoTx6qpoieATMh/BALBc_no3_raw.zip) |[download](https://syncandshare.lrz.de/dl/fiD9e98baTK3FWC9iPhLQWd8/BALBc_no3.zip) |
`C57BL_6_no1`|[download](https://syncandshare.lrz.de/getlink/fiToWvNWjmf2165TtStGWG3a/C57BL_6_no1_raw.zip) |[download](https://syncandshare.lrz.de/dl/fiVTuLxJeLrqyWdMBy5BGrug/C57BL_6_no1.zip) |
`C57BL_6_no2`|[download](https://syncandshare.lrz.de/getlink/fiTs8xQM7yGuD4dSc4uvEWa4/C57BL_6_no2_raw.zip) |[download](https://syncandshare.lrz.de/dl/fiNFpZd5S9NYvUYzNwLgf5gW/C57BL_6_no2.zip) |
`C57BL_6_no3`|[download](https://syncandshare.lrz.de/getlink/fiAmLSy2j5CePwoWcZhZc6Hz/C57BL_6_no3_raw.zip) |[download](https://syncandshare.lrz.de/dl/fi3Z62oab67735GLQXZyd2Wd/C57BL_6_no3.zip) |
`CD1-E_no1`|[download](https://syncandshare.lrz.de/getlink/fiSDag6MmmdUqhNmZAMgMb2U/CD1-E_no1_raw.zip) |[download](https://syncandshare.lrz.de/dl/fiQs4v6kXvGBviqnuT7BAxjK/CD1-E_no1.zip) |
`CD1-E_no2`|[download](https://syncandshare.lrz.de/getlink/fiVtFCYtugvPwvvCSSfWPFzc/CD1-E_no2_raw.zip) |[download](https://syncandshare.lrz.de/dl/fiJf6ukkGCdUQwXBKd4Leusp/CD1-E_no2.zip) |
`CD1-E_no3`|[download](https://syncandshare.lrz.de/getlink/fiMCHhkfr33bFxr2guDWtYYL/CD1-E_no3_raw.zip) |[download](https://syncandshare.lrz.de/dl/fiBkjGNxm7XW5R4gFTWp5MFP/CD1-E_no3.zip) |
`C57BL_6-K1` |[download](https://syncandshare.lrz.de/getlink/fi8ZViiaHhwJhyvHCGbVV47y/C57BL_6-K18_raw.zip) |[download](https://syncandshare.lrz.de/getlink/fi9ewjPWq5EmUjVDGDbcR28Q/C57BL_6-K18.zip) |
`C57BL_6-K2` |[download](https://syncandshare.lrz.de/getlink/fi3RtXSK4pUMks59HF6oPGWm/C57BL_6-K19_raw.zip) |[download](https://syncandshare.lrz.de/getlink/fiNryxTQPREgrXRrcWhm2xW/C57BL_6-K19.zip) |
`C57BL_6-K3` |[download](https://syncandshare.lrz.de/getlink/fiNyBFDHxYwG4ZXW8iSK5W56/C57BL_6-K20_raw.zip) |[download](https://syncandshare.lrz.de/getlink/fiP6oRLaqL9vJYuGfhCS9xbP/C57BL_6-K20.zip) |
`Synth. Graph 1`|[download](https://syncandshare.lrz.de/getlink/fiBRoY7z2c3YbgVMXfs5nnUc/synthetic_graph_1_raw.zip) |[download](https://syncandshare.lrz.de/getlink/fiXfSD14pKGM54L5BqZxF8vF/synthetic_graph_1.zip) |
`Synth. Graph 2`|[download](https://syncandshare.lrz.de/getlink/fiR9Ktp26Zqhv23gmUBkzg5N/synthetic_graph_2_raw.zip) |[download](https://syncandshare.lrz.de/getlink/fiEDhbBHmqawVwKaBeWwHgT8/synthetic_graph_2.zip) |
`Synth. Graph 3`|[download](https://syncandshare.lrz.de/getlink/fi6gyGJ9Btx5U2AKzoegyscn/synthetic_graph_3_raw.zip) |[download](https://syncandshare.lrz.de/getlink/fiPvTKvqhqNtQ8B6UyGfbvGi/synthetic_graph_3.zip) |
`Synth. Graph 4`|[download](https://syncandshare.lrz.de/getlink/fi7ZSVgucX2jyn9hBRtnwPKa/synthetic_graph_4_raw.zip) |[download](https://syncandshare.lrz.de/getlink/fiFq7BVkRZekbBYQSVYX8L6K/synthetic_graph_4.zip) |
`Synth. Graph 5`|[download](https://syncandshare.lrz.de/getlink/fiFfcKCNE2uK3d5CJ8wxBMo8/synthetic_graph_5_raw.zip) |[download](https://syncandshare.lrz.de/getlink/fi5dos737XVZxuyqQ5gmUW6p/synthetic_graph_5.zip) | 

We are currently verifying the C57BL_6-K** graph representations with the Kleinfeld Lab at UC San Diego. As the raw data is not processed using Voreen (our default graph generation pipeline),
we are in contact with the authors of the original paper and want to ensure a similar interface to this data.

#### 3. Generate Atlas features
Go to [`./source/feature_generation/atlas_annotation/`](./source/feature_generation/atlas_annotation/) and run `generate_node_atlas_labels.py` with arguments of `--node_list` and `--edge_list`
#### 4. Convert to Pytorch-Geometric Dataloader
Go to [`./source/pytorch_dataset/`](./source/pytorch_dataset/) and run `link_dataset.py` and `node_dataset.py` to create pytorch-geometric compatible dataset for link-prediction and node-classification task.
#### 5. Convert to OGB Dataloader

1. **For Graph** `G`


- Go to [`./source/ogb_dataset/link_prediction/`](./source/ogb_dataset/link_prediction/)

and run `python3 generate_ogbl_dataset.py --dataset BALBc_no1 --splitting_strategy random --train_val_test 0.8 0.1 0.1 --data_root_dir data` 

Argument list:

      --dataset: from the list of `Dataset Name` in the table above
      --splitting_strategy: either `random` or `spatial`
      --seed: if any other random split than the default one
      --train_val_test: if any other train val test split % than the default one
      --data_root_dir: root directory where the data will be stored

- Subsequently run `update_ogbl_master.sh` for compiling the ogb repository locally.

2. **For Line Graph** `L(G)`


- Go to [`./source/ogb_dataset/node_classification/`](./source/ogb_dataset/node_classification/)

and run `python3 generate_ogbn_dataset.py --dataset BALBc_no1 --train_val_test 0.8 0.1 0.1 --data_root_dir data`

Argument list:

      --dataset: from the list of `Dataset Name` in the table above
      --seed: if any other random split than the default one
      --train_val_test: if any other train val test split % than the default one
      --data_root_dir: root directory where the data will be stored

- Subsequently run `update_ogbn_master.sh` for compiling the ogb repository locally.

- We use the following options

```bash
Enter indices of desired features (Use "," to separate them): 0,1,2
Enter feature index of desired label: 4
Choose between a certain number of balanced classes (bc) or define classes by pixel boundaries (pb): pb
Enter desired radius boundaries as pixel values (Use "," to separate them): 5,13.33
```
- Subsequently run `update_ogbn_master.sh` for node-classification task.


### Dataloader Instruction

#### 1. **Pytorch-geometric Dataloader**

We provide PyG dataset classes for link and node prediction tasks in [`./source/pytorch_dataset/`](./source/pytorch_dataset/). Utilize `LinkVesselGraph` and `NodeVesselGraph` respectively. See the [`./vesselgraph.ipnb`](./vesselgraph.ipnb) for a toy example.

#### 2. **OGB Dataloader**

We store our graphs as OGBN (OGB Node Prediction) and OGBL (Link Prediction) graphs. All algorithms in [`./source/baseline_models/`](./source/baseline_models/) rely on OGB Dataloaders and process the graphs in OGB compatible format.

### Baseline Instruction

All baseline model can be run out-of-the-box with the following commands which automatically downloads the processed dataset.

#### 1. **Link Prediction task**

1.1 **Training**

To create the node embeddings go to [`./source/baseline_models/link_prediction/OGB_Node2Vec/`](./source/baseline_models/link_prediction/OGB_Node2Vec/) and run`python3 node2vec.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr`

Subsequently go to [`./source/baseline_models/link_prediction/`](./source/baseline_models/link_prediction/) and enter a `MODEL` directory to run

Model Name | Script
-----|---------------
Adamic Adar|`python3 seal_link_pred.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr --use_heuristic AA`
Common Neighbors |`python3 seal_link_pred.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr --use_heuristic CN`
Resource Allocation |`python3 seal_link_pred.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr --use_heuristic RA`
Matrix Factorization |`python3 mf.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr`
MLP|`python3 mlp.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr` 
GCN GCN |`python3 gnn.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr`
GCN GCN + embeddings |`python3 gnn.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr --use_node_embedding`
GCN SAGE + embeddings|`python3 gnn.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr --use_node_embedding --use_sage  --num_layers 3 --hidden_channels 128`
GCN SAGE |`python3 gnn.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr --use_sage  --num_layers 3 --hidden_channels 128`
SEAL |`python3 seal_link_pred.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr --dynamic_train --dynamic_val --dynamic_test --use_feature`


For the dataset name, we follow the OGB convention. For example, to run the `BALBc_no1` whole brain with a spatial splitting strategy, and without edge features (edge attributes),
use `python3 gnn.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr`.

We also provide a memory-friendly alternative (a selected Region of Interest of the entire graph). To run the models on the selected region of interest, 
use `python3 gnn.py --dataset ogbl-link_vessap_roi3_spatial_no_edge_attr`.

If you are unsure what options are available, simply run the following command that will list all available datasets:

use `python3 gnn.py --dataset ogbl-xyz`.

1.2 **Testing**

*Download Trained Weights* and place them in the respective model folder
|Model Name | Checkpoint | 
-----|---------------
Adamic Adar|[heuristic, not applicable]
Common Neighbors |[heuristic, not applicable]
Resource Allocation |[heuristic, not applicable]
Matrix Factorization |[download](https://syncandshare.lrz.de/getlink/fi2SY3S11Z1jdnvPnh5xn5RK/MF)
MLP|[download](https://syncandshare.lrz.de/getlink/fi9RWSLJ9Zmdbr1n74zDbZ9R/MLP)
GCN GCN   |[download](https://syncandshare.lrz.de/getlink/fiLN8QNyXdHm3jNUkgTya3SA/GNN_GCN)
GCN GCN + embeddings |[download](https://syncandshare.lrz.de/getlink/fiLiTAy7xgNJp69SyYjKj6jc/GNN_GCN_embeddings)
GCN SAGE + embeddings |[download](https://syncandshare.lrz.de/getlink/fiEb3iZrrU15PGkNemiZLiXi/GNN_SAGE_embeddings)
GCN SAGE |[download](https://syncandshare.lrz.de/getlink/fi2TtEzMKUSxastBvEGmUjzx/GNN_SAGE)
SEAL |[download](https://syncandshare.lrz.de/getlink/fiGbhGhyYFCyqGfnWqsjKbHb/SEAL)

Go to [`./source/baseline_models/link_prediction/`](./source/baseline_models/link_prediction/) and select go a `MODEL` directory to run

e.g. to run GCN, one needs to use the following `python3 gnn.py --dataset ogbl-BALBc_no1_spatial_no_edge_attr --load_state_dict --test_only`

The same applies for the other models with two additional flags `--load_state_dict` and `--test_only`

#### 2. **Node Classification task**

2.1 **Training**

Go to [`./source/baseline_models/node_classification/`](./source/baseline_models/node_classification/) and select a `MODEL` directory to run

Model Name | Script
-----|---------------
GCN | `python3 gnn.py --dataset ogbn-BALBc_no1_pb_minRadiusAvg`
GraphSAGE | `python3 gnn.py --dataset ogbn-BALBc_no1_pb_minRadiusAvg --use_sage --num_layers 4 --hidden_channels 128`
GraphSAINT | `python3 graph_saint.py --dataset ogbn-BALBc_no1_pb_minRadiusAvg --num_layers 4 --hidden_channels 64 --walk_length 7`
SIGN | `python3 sign.py --dataset ogbn-BALBc_no1_pb_minRadiusAvg --hidden_channels 128`
Cluster-GCN | `python3 cluster_gcn.py --dataset ogbn-BALBc_no1_pb_minRadiusAvg --num_layers 4 --num_partitions 9`
MLP | `python3 mlp.py --dataset ogbn-BALBc_no1_pb_minRadiusAvg`
SpecMLP-W + C&S | `python3 mlp_cs.py --dataset ogbn-BALBc_no1_pb_minRadiusAvg`
SpecMLP-W + C&S + Node2Vec| `python3 mlp_cs.py --dataset ogbn-BALBc_no1_pb_minRadiusAvg --use_embed`

2.2 **Testing**

*Download Trained Weights* and place them in the respective model folder
|Model Name | Checkpoint | 
-----|---------------
GCN|[download](https://syncandshare.lrz.de/getlink/fi7P51t9pk7Tm7gU83ABi7x2/gnn)
GraphSAGE |[download](https://syncandshare.lrz.de/getlink/fiN1GyuX2NVopUoKaNpahQYm/gnn_sage)
GraphSAINT |[download](https://syncandshare.lrz.de/getlink/fiQrPQvm2f6rdCe3Z1bAbRc4/graph_saint)
SIGN |[download](https://syncandshare.lrz.de/getlink/fiB1ZZfXf92RN89mWZuDuVZR/sign)
Cluster-GCN |[download](https://syncandshare.lrz.de/getlink/fiE5MCmNaEoUnHrFVCqYfrzL/cluster_gcn)
MLP|[download](https://syncandshare.lrz.de/getlink/fiH4GzQvCtS728iDec4mGWeq/mlp)
SpecMLP-W + C\&S |[download](https://syncandshare.lrz.de/getlink/fiKJdZz19iAQCPmPxrFNPRQ9/mlp_cs)
SpecMLP-W + C\&S + N2Vec|[download](https://syncandshare.lrz.de/getlink/fiWahsBTS6uAvEFFLqpzaThN/mlp_cs_node2vec)

Go to [`./source/baseline_models/node_classification/`](./source/baseline_models/node_classification/) and select go a `MODEL` directory to run

e.g. to run GNN, one needs to use the following `python3 gnn.py --model_states STATE_DICT_NAME --test_only --dataset DATASET_NAME`

The same applies for the other models.

## Contribute 

We are a living and continously maintained repository! Therefore, we welcome contributions of additional datasets and methods! There are multiple ways to contribute; if you are willing to share whole brain segmentations and graphs .... 

## Acknowledgement 
#### 1. Link to the Baseline Dataset
1. Vessap Dataset: [[website](http://discotechnologies.org/VesSAP/)][[paper](https://doi.org/10.1038/s41592-020-0792-1)]
2. Kleinfeld Dataset: [[website](https://neurophysics.ucsd.edu/software.php)][[paper](https://doi.org/10.1016/j.neuron.2021.02.006)]
3. Synthetic Dataset: [[website](https://github.com/giesekow/deepvesselnet/wiki/Datasets)][[paper](https://doi.org/10.1016/j.media.2012.04.009)]

#### 2. Link to the Baseline Models
1. GCN: [[code](https://github.com/snap-stanford/ogb/tree/master/examples)][[paper](https://arxiv.org/abs/1609.02907)]
2. SAGE: [[code](https://github.com/snap-stanford/ogb/tree/master/examples)][[paper](https://arxiv.org/abs/1706.02216)]
3. GraphSAINT: [[code](https://github.com/snap-stanford/ogb/tree/master/examples)][[paper](https://arxiv.org/abs/1907.04931)]
4. SIGN: [[code](https://github.com/snap-stanford/ogb/tree/master/examples)][[paper](https://arxiv.org/abs/2004.11198)]
5. SpecMLP: [[code](https://github.com/ytchx1999/PyG-ogbn-products/tree/main/spectral%2Bmlp%2Bcs)][[paper](https://arxiv.org/abs/2010.13993)]
6. SEAL: [[code](https://github.com/facebookresearch/SEAL_OGB)][[paper](https://arxiv.org/pdf/2010.16103.pdf)]
