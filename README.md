# Lumbar Spine Segmentation Project

## Dataset
A total of 514 lumbar MRI scans. All are in sagittal views. 

Dataset can be downloaded from: https://data.mendeley.com/datasets/k57fr854j2/2​

A signle MRI scan slice size: a grayscale image of 320 x 320​ (3 x 320 x 320, where R=G=B).

Bone segmentation mask downloaded from: https://data.mendeley.com/datasets/k3b363f3vz/2

## Objective

A multi-class bone segmentation task; 7 different classes as follows:

0: background <br>
1: L1 <br>
2: L2 <br>
3: L3 <br>
4: L4 <br>
5: L5 <br>
6: S1

## Architecture
A standard 2d unet is used for the binary segmentation problem. It is pretrained on the brain MRI segmentation dataset. The concept of transfer learning is applied here.

For the multi-class segmentation, DeepLabV3 (ResNet-50) architecture is used. Trained from scratch.

## Results
The model's performance is evaluated using the dice coefficient.

The dice coefficient is calculated for every scan in the test set. After 35 epochs, the median dice score is 0.89 (training time is approximately 3 hours). 

The lumbar_spine_binary.ipynb code simplifies the objective in an attempt to debug the lumbar_spine.ipynb code. 

The segmentation accuracy could be improved by running more epochs. The accuracy continues to go down for the entirety of the training period.

## Future Modifications
Apply the trained model to the cervical spine dataset.

Consider adding data augmentation (especially horizontal flip) as necessary.