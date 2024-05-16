# Text-GCN 

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A PyTorch implementation of "Graph Convolutional Networks for Text Classification." (AAAI 2019)

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

