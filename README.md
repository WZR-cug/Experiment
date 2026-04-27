# DMR-ACM MM2020
源代码：https://github.com/luost26/DMRDenoise

## 环境配置

### Recommended Environment

The code has been tested with the following environment:

| Package                | Version |
| ---------------------- | ------- |
| PyTorch                | 1.5.1   |
| CUDA and NVCC Compiler | 10.0    |
| scikit-learn           | 0.23.1  |
| h5py                   | 2.10.0  |
| PyTorch Lightning      | 0.7.6   |

### Install via Conda

We provide a yaml file that allows instantaneous environment setup. Run the following command and it will create a conda environment named `DMRDenoise` with all required packages installed:

```bash
conda env create -f environment.yml
conda activate DMRDenoise
```

Next, compile the EMD operator. Note that this step requires CUDA NVCC compiler:

```bash
cd ./ops/emd
python setup.py install
```

### Install Manually

You may also set up the environment manually. We provide the instruction as follows:

```bash
# Create a conda environment
conda create --name DMRDenoise python=3.6
conda activate DMRDenoise
# Install required packages
conda install -y pytorch=1.5.1 torchvision=0.6.1 cudatoolkit=9.2 -c pytorch
conda install -y scikit-learn=0.23.1
conda install -y -c conda-forge h5py=2.10.0 pytorch-lightning=0.7.6
# Compile the EMD operator
# [NOTICE] This step requires CUDA NVCC compiler
cd ./ops/emd; python setup.py install; cd ../../
```

## 数据
待测数据放在data文件夹下

## Train
有监督训练:
```bash
python train.py
```

无监督训练:
```bash
python train.py --loss_ds None --loss_rec unsupervised
```

## 测试
注意将名称替换掉
```bash
python denoise.py --input <input_xyz> --output <output_xyz> --ckpt ./pretrained/supervised/epoch=153.ckpt
```



W
