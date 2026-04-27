# GPDNet-ECCV2020
源代码：https://github.com/diegovalsesia/GPDNet

## 环境配置
```
conda create -n GPDNet python=2.7
pip install numpy
pip install scipy
pip install h5py
pip install tensorflow-gpu==1.12
pip install point-cloud-utils==0.31.0
```

# Code structure
Code/ : Python source code for training/testing and the network model
Dataset/ : Shapenet training and testing data
log_dir/ : log files and tensorboard events
Results/ : saved checkpoints and denoised point clouds 

# Dataset
Download the Dataset directory from: https://www.dropbox.com/sh/nwdlzgnt987yjma/AAAi8q0E6yioxk5I_BkUpZE5a?dl=0

# Pretrained models
Pretrained models are included for the MSE-SP loss and 16-NN at standard deviations 0.01,0.015,0.02. Results might be slightly different from the ones in the paper.

# Test
```
./launcher_test.sh
```
Denoised point clouds and C2C metrics will be written to Results directory. 

# Train
```
./launcher_train.sh
```
Checkpoints will be written to the Results directory.

# Notes
Code is partially based on this project (https://github.com/diegovalsesia/gcdn). Check out its documetation for more details on the parameters in config.py.
Training and tested was run on
```
CPU: AMD Ryzen 1 1700
RAM: 32 GB
GPUs: 1x Nvidia Quadro P6000 (24 GB)
```
