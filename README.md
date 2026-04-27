# PointCleanNet-CGF2020
源代码：https://github.com/mrakotosaon/pointcleannet

## Setup
Install required python packages, if they are not already installed ([tensorboardX](https://github.com/lanpa/tensorboard-pytorch) is only required for training):
``` bash
pip install numpy
pip install scipy
pip install tensorboardX
```


Clone this repository:
``` bash
git clone https://github.com/mrakotosaon/pointcleannet.git
cd pointcleannet
```


Download datasets:
``` bash
cd data
python download_data.py --task denoising
python download_data.py --task outliers_removal
```


Download pretrained models:
``` bash
cd models
python download_models.py --task denoising
python download_models.py --task outliers_removal
```

 ## Data

Our data can be found here: https://nuage.lix.polytechnique.fr/index.php/s/xSRrTNmtgqgeLGa .

It contains the following files:
- Dataset for denoising
- Training set and test set for outliers removal
- Pre-trained models for denoising and outliers removal

In the datasets the input and ground truth point clouds are stored in different files with the same name but with different extensions.
- For denoising: `.xyz` for input noisy point clouds, `.clean_xyz` for the ground truth.
- For outliers removal: `.xyz` for input point clouds with outliers, `.outliers` for the labels.



## Removing outliers
To classify outliers using default settings:
``` bash
cd outliers_removal
mkdir results
python eval_pcpnet.py
```

## Denoising
To denoise point clouds using default settings:
``` bash
cd noise_removal
mkdir results
./run.sh
```
(the input shapes and number of iterations are specified in run.sh file)


## Training
To train PCPNet with the default settings:
``` bash
python train_pcpnet.py
```
