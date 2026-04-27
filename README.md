# IterativePFN-CVPR2023
源代码：https://github.com/ddsediri/IterativePFN

## 环境配置
```
conda create -n IterativePFN python=3.7
conda activate IterativePFN
conda install pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch
conda install -c fvcore -c iopath -c conda-forge fvcore iopath
conda install -c bottler nvidiacub
conda install pytorch3d -c pytorch3d
conda install pyg -c pyg
pip install pytorch-lightning==1.7.6
pip install point-cloud-utils==0.27.0
pip install plyfile
pip install pandas
```

## 数据
将待测数据放在data文件夹下

## 训练
```
./launcher_train.sh
```

## 测试
将预训练模型放在pretrained文件夹下
```
./launcher_test.sh
```

