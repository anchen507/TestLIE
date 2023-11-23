# Unsupervised Low-Light Image Enhancement: Where Data-Driven Learning Meets Prior-Guided Designing

This repository contains the implementation of the Unsupervised Low-Light Image Enhancement method proposed in the paper titled "Unsupervised Low-Light Image Enhancement: Where Data-Driven Learning Meets Prior-Guided Designing".

## Abstract

Existing data-driven low-light image enhancement (LIE) methods require large amounts of training samples, and the learned representation may be invalid for real-world scenes due to the data discrepancy. To address this problem, this work proposes DP-LIE, an unsupervised LIE method driven by both data and priors. Unlike the existing methods that learn unexplainable high-dimensional features for end-to-end mapping, DP-LIE focuses on learning prior-guided parametric maps with definite meanings, enabling the low-light images to be brightened from an interpretable prior-based perspective. To this end, we delicately design a simple yet effective prior-guided network-assisted LIE formulation, which elaborately bonds the data-driven representations with the traditional priors. The embedded priors narrow the solution space of the LIE model, allowing it to be efficiently trained with fewer samples. Notably, even trained with just a single low-light input image, the proposed method (denoted as DP-LIE-S) achieves comparable performances with SOTA unsupervised LIE methods. Moreover, due to its low dependency on training data, the proposed DP-LIE exhibits excellent generalization performance across various datasets.


## Requirements
For optimal usage of this code, it is recommended to install the following packages:
- Python 3.6
- torch 1.10.1
- torchvision 0.11.2
- sympy 1.9
- numpy 1.19.5
- pillow 8.4.0
- pyiqa 0.1.7
- matplotlib 3.3.4
- opencv-python 4.5.2

## Usage
### Training DP-LIE-M: 
- python run_DPLIEM.py (will be released soon!)

### Testing DP-LIE-M:
- python test_DPLIEM.py --model_path './chinkpoint/model.pth.tar' --dataset_dir './dataset/' --evaldata_list 'Demo.txt' --output_image_path 'Output/DP-LIE-M/' 

### Training/testing DP-LIE-S:
- python run_DPLIES.py --dataset_dir './dataset/' --evaldata_list 'Demo.txt' --evaldata_list 'Demo.txt' --output_image_path 'Output/DP-LIE-S/' --nEpochs 200

## Data Preparation

### Dataset Description

This code is designed to work with the following datasets:

- LOL-test
- LOL-real
- DICM
- VV
- MEF
- LIME
- NPE

### Data Organization

1. **Download the Datasets**:

   Download the LOL-test, LOL-real, DICM, VV, MEF, LIME, and NPE datasets from their respective sources. Place the downloaded datasets in a directory named `data`.

2. **Dataset Structure**:

   Organize the downloaded datasets in the `data` directory as follows:

   ```plaintext
   data/
   ├── LOL-test/
   ├── LOL-real/
   ├── DICM/
   ├── VV/
   ├── MEF/
   ├── LIME/
   ├── NPE/
   
3. **Generate datalist**：
Pair the corresponding low-light images and their ground truth images (if available) in a format similar to 'Demo.txt':
```plaintext
data/normal_light/test1.png data/low_light/test1.png
data/normal_light/test2.png data/low_light/test2.png
data/normal_light/test3.png data/low_light/test3.png
...

For non-reference (no ground truth) datasets, both columns can list low-light images as:
data/low_light/test1.png data/low_light/test1.png
data/low_light/test2.png data/low_light/test2.png
data/low_light/test3.png data/low_light/test3.png
...
##
