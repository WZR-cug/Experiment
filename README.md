# PointCleanNet-CGF2020
源代码：https://github.com/mrakotosaon/pointcleannet

## 环境配置
``` bash
conda create -n PCN python=2.7
conda activate PCN
conda install pytorch==1.0.0 torchvision==0.2.1 cuda100 -c pytorch
pip install numpy
pip install scipy
pip install tensorboardX
```

## 数据
将待测试的数据集放在/data文件夹里

## 下载预训练模型
``` bash
cd models
python download_models.py --task denoising
python download_models.py --task outliers_removal
```
## 训练
``` bash
python train_pcpnet.py
```

## 测试
``` bash
cd noise_removal
mkdir results
./run.sh
```



