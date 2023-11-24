## Notice

The code provided here is not executable and is solely meant to offer additional insight into the implementation details of DP-LIE. 
The complete and executable code will be released to the public following the acceptance of the paper.

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
  
## Pretrained model
- The chinkpoint will be released after acceptance!

## Usage
### Training DP-LIE-M: 
- python run_DPLIEM.py (will be released after acceptance!)

### Testing DP-LIE-M:
- python test_DPLIEM.py --model_path './chinkpoint/model.pth.tar' --dataset_dir './dataset/' --evaldata_list 'Demo.txt' --output_image_path 'Output/DP-LIE-M/' 

### Training/testing DP-LIE-S:
- python run_DPLIES.py --dataset_dir './dataset/' --evaldata_list 'Demo.txt'  --output_image_path 'Output/DP-LIE-S/' --nEpochs 200

python run_DPLIES.py --dataset_dir './../../data/' --evaldata_list 'LOL-V1_test.txt' --output_image_path 'Output/DP-LIE-S/' --nEpochs 200

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
