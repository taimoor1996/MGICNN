
# Multi-scale Gradual Itegration Convolutional Neural Network for False Positive Reduction in Pulmonary Nodule Detection

This repository contains code to train and test MGI-CNN. 

## Hardware and Software

### Software requirements

For data processing: SimpleITK, Scipy

```pip install SimpleITK scipy```

For training: Ubuntu 16.04, Python 3.6, Tensorflow 1.10

(Optional) GPUtil

```pip install GPUtil```

### Hardware and training duration

Each fold takes about 12 hours to run 100 epochs using Nvidia GTX 1080 ti. Note that all experiments in our paper is based on 40<sup>th</sup> epoch.


## Usage

For training:

```python main.py --data_path=PATH --summ_path_root=PATH --fold=0 --maxfold=5 --multistream_mode=0 --model_mode=0 --train```

For testing:

```python main.py --data_path=PATH --summ_path_root=PATH --fold=0 --maxfold=5 --multistream_mode=0 --model_mode=0 --test --tst_model_path=PATH --tst_epoch=40```

1. Specify your data path (--data_path) and path to save your results and summary (--summ_path_root).
2. Specify fold to train (--fold) and maximum number of folds (--maxfold).
3. Specify which multistream mode to use (--multistream_mode). (0-element(proposed), 1- concat, 2-1x1 comv)
4. Specify which model to use (--model_mode). ()0-proposed, 1-RI , 2-LR, 3-ZI, 4- ZO)
5. Specify train or test (--train or --test and --tst_model_path/--tst_epoch).

## Authors

Bum-Chae Kim, Jee Seok Yoon, and prof. Heung-Il Suk*
*corresponding author: hisuk@korea.ac.kr

Machine Intelligence Lab.,
Dept. Brain & Cognitive Engineering. 
Korea University, Seoul, Rep. of Korea.


## Lung Nodula Analysis 2016 (LUNA16) 

This project for pulmonary nodule detection systems FP reduction.
We use LUNA16 challenge dataset.

- https://luna16.grand-challenge.org/ 

## Results

We participated in the competition and got the following CPMs:

- MILAB_ConcatCAD: rank 3 (2017.11.25)
- MILAB_RedCAD@: rank 8 (2017.11.25)

@:The submissions with '@'' used the initially provided 
list of nodule candidates computed using fewer candidate detection algorithms.

last update date: 2018.12.20.

