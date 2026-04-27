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

## 数据
把数据文件夹命名为Dataset，然后放在根目录下

## 训练
```
./launcher_train.sh
```

## 测试
```
./launcher_test.sh
```


