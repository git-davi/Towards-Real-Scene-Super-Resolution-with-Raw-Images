### [**THIS WORK IS NOT MINE, I WOULDN'T GIVE ANY SUPPORT**]
### All credits to the real authors!!

# Towards Real Scene Super-Resolution with Raw Images

This repository is for the rawSR introduced in the following CVPR paper:
Xiangyu Xu, Yongrui Ma, Wenxiu Sun, "Towards Real Scene Super-Resolution with Raw Images", CVPR 2019
[[paper]](https://arxiv.org/abs/1905.12156)


## Contents

1. [Environment](#1)
2. [Train](#2)
3. [Test](#3)


<h3 id="1">Environment</h3>
Our model is trained and tested through the following environment on Ubuntu:

- Python: v2.7.5 
- tensorflow with gpu: v1.9.0
- rawpy: v0.12.0
- numpy: v1.15.3
- scipy: v1.1.0


<h3 id="2">Train</h3>

* Prepare training data
    1. Download the raw dataset for blind super-resolution (13040 training and 150 validation images) from [dataset]( https://drive.google.com/file/d/1U0EvzwAB7Dq7bLeit595gNpEKU4ya0wl/view?usp=sharing)
    2. Place the downloaded dataset to 'RawSR/'

* Begin to train
    1. cd into 'RawSR/code' and run the following script to train our model:
        ```
        python train_and_test.py
       ```
	   
    2. You can use 'RawSR/parameters.py' to play with the parameters according to the annotations. Our default setting trains the model from 0 epoch without any pretraining, and the validation images will be leveraged to test model performance per 10 epochs. 

<h3 id="3">Test</h3>

* Prepare testing data
    * Synthetic data
        1. Download the synthetic testing dataset (150 images) from [Google Drive](https://drive.google.com/open?id=1hoXGO_4vWRmRFoMIiQ32KwN_12kgNn7j) [BaiduNetdisk](https://pan.baidu.com/s/1z972Ic5X3zmMdwkMeOwA2w)
        2. Place the downloaded dataset to 'RawSR/Dataset/Synthetic/TESTING' or modify the 'TESTING_DATA_PATH' of parameters.py  to the corresponding path.
    
    * Real data
        1. We provide some real examples in [Google Drive](https://drive.google.com/open?id=1aoS_5aWVOo9IRT25MwrSiWU4uOVkysl6) [BaiduNetdisk](https://pan.baidu.com/s/1exZYhv6_l9REEL_syLxr0w). You can also test your own raw images.
        2. Place the downloaded dataset or your prepared raw images (like .CR, .RAW, .NEF and etc.) to 'RawSR/Dataset/REAL' or modify the 'REAL_DATA_PATH' of 'parameters.py' to corresponding path.
    
* Begin to test
    * Synthetic data
        1. Set 'TRAINING' and 'TESTING' of 'parameters.py' to be False and True respectively.
        2. Download the pretrained models through [Google Drive](https://drive.google.com/open?id=14f5Oif-LVW-WvNeuKRK2kn3GH5JW5OtW) [BaiduNetdisk](https://pan.baidu.com/s/1vXVGVx4zgD5NiroHUpv-Mg), and then place it to 'RawSR/log_dir'.
    
    * Real image
        1. Set 'REAL' of 'parameters.py' to be True.
        2. Download the pretrained models as above, and then place it to 'RawSR/log_dir'.
    
        And then, cd 'RawSR/code' and run the following script for testing:
            ```
            python train_and_test.py
            ```
        
        The testing results can be found in the path defined in 'RESULT_PATH' in 'parameters.py'.



