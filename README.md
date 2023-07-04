# Text-GCN 

[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/graph-convolutional-networks-for-text/text-classification-on-r8)](https://paperswithcode.com/sota/text-classification-on-r8?p=graph-convolutional-networks-for-text)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![codebeat badge](https://codebeat.co/badges/03853262-a233-4faa-911f-e03df5eda8fa)](https://codebeat.co/projects/github-com-codekgu-text-gcn-master)

A PyTorch implementation of "Graph Convolutional Networks for Text Classification." (AAAI 2019)

![text_gcn](text_gcn.png)

This repository contains a PyTorch implementation of 
> Graph Convolutional Networks for Text Classification. 
> Liang Yao, Chengsheng Mao, Yuan Luo.
> AAAI, 2019. [\[Paper\]](https://arxiv.org/abs/1809.05679)

A reference Tensorflow implementation is accessible [\[here\]](https://github.com/yao8839836/text_gcn).

## Requirements
This repo uses python 3.6 and the following PyTorch packages:

- torch==1.3.1
- torch-cluster==1.2.4
- torch-geometric==1.1.2
- torch-scatter==1.1.2
- torch-sparse==0.4.0
- torchvision==0.4.0

I also use [comet.ml](https://www.comet.ml/site/) for experiment tracking

## Included Datasets

The included datasets are a twitter asian prejudice [dataset](https://arxiv.org/abs/2005.03909), reuters 8, and AG's news topic classification [dataset](https://github.com/mhjabreel/CharCnn_Keras/tree/master/data/ag_news_csv).

For a new dataset, prepare a `[dataset_name]_labels.txt` and `[dataset_name]_sentences.txt` in `/data/corpus` in which each line corresponds to a document and its corresponding label. 
Use `prep_data.py` to further clean `[dataset_name]_sentences.txt`.
The script will generate a  `[dataset_name]_sentences_clean.txt`
 
The following is an example of the constructed text graph for the twitter dataset. Green represents text nodes and red represents document nodes.
![twitter text graph](https://github.com/codeKgu/text-gcn/blob/master/data/text_graphs/twitter_text_graph_nohashtag.png)

## Running the model

To run the model simply change the model and dataset configurations in `config.py`. You can also enter your own cometml information to see the results and experiment running in the browser. 
After model configuration, simply run 
```
$ python main.py
```

## Results
Some initial results I have obtained using hyperparameters from the TextGCN paper are

Dataset | Accuracy
--------|---------
twitter_asian_prejudice | 0.754
r8_presplit | 0.963
ag_presplit | 0.907
ag_presplit | 0.907
fake_news | 0.846

