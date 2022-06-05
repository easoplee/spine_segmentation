# Lumbar Spine Segmentation Project

## Dataset
A total of 514 lumbar MRI scans. All are in sagittal views. 

Dataset can be downloaded from: https://data.mendeley.com/datasets/k57fr854j2/2​

A signle MRI scan slice size: a color image of 320 x 320​ (3 x 320 x 320).

Bone segmentation mask downloaded from: https://data.mendeley.com/datasets/k3b363f3vz/2

## Objective

A multi-class bone segmentation task; 7 different classes as follows:

0: background <br>
1: L1
2: L2
3: L3
4: L4
5: L5
6: S1

## Architecture
A standard 2d unet is used.

## Results
The model predicts every pixel as background. 
Attempts to fix this problem include decreasing learning rate and increasing batch size.

The lumbar_spine_binary.ipynb code simplifies the objective in an attempt to debug the lumbar_spine.ipynb code. The simplified objective is to perform binary segmentation that classifies each pixel as background and bone. The model still predicts every pixel as background.

Since over 94% of the pixels are labeled as background, class imbalance issue should be discussed.

## Future Modifications
Explore different optimizers.

Consider adding more regularization (dropout, BatchNormalization, InstanceNormalization, etc.).

Consider replacing ReLU with other activation functions such as tanh.