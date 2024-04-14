# FMSS: Fusion Modality-Specific and Modality-Shared Features for Multi-Hop Reasoning over Multi-Modal Knowledge Graph

This repository provides the official PyTorch implementation of the research paper **FMSS: Fusion Modality-Specific and Modality-Shared Features for Multi-Hop Reasoning over Multi-Modal Knowledge Graph**. It will update soon. Thanks for your attention.

### Requirements

- python >= 3.6
- torch >= 1.8.1
- torchvision >= 0.9.2
- torch-geometric >= 2.0.3
- torch-sparse >= 0.6.12
- torch-scatter >= 2.0.6
- dgl-cu111 >= 0.6.1
- gensim >= 4.2.0
- tqdm
- pandas
- rdflib

### Dataset

```shell
# WN9-IMG-TXT
FBIMG/train/valid/test
# FB-IMG-TXT
WN9IMG/train/valid/test
```

### How to Run

**Step 1**: pre-process the dataset

```shell
./experiment.sh configs/<dataset>.sh --process_data <gpu-ID>
```

**Step 2**: get **[PageRank](https://github.com/timothyasp/PageRank)** score

You can get code from https://github.com/timothyasp/PageRank

```shell
python pageRank.py ./raw.csv directed > raw.pgrk
```

**Step 3**: get pretrain embeddings 

```shell
The pretrain embeddings of multi-modal knowledge can be downloaded from following link:
Link：https://share.weiyun.com/6I3sTANu 
Code：q78wm7
```

**Step 4**: train MADC model

```shell
./experiment-emb.sh configs/<dataset>-<model>.sh --train <gpu-ID>
```

**Step 5**: train model

```shell
./experiment-rs.sh configs/<dataset>-rs.sh --train <gpu-ID> 
```

**Step 6**: test model

```shell
./experiment-rs.sh configs/<dataset>-rs.sh --inference <gpu-ID> 
```

## Cite

