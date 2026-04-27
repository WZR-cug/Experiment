# Pointfilter-TVCG2021
源代码：https://github.com/dongbo-BUAA-VR/Pointfilter

## 环境配置
``` bash
conda create -n Pointfilter python=3.6
pip install numpy
pip install scipy
pip install plyfile
pip install scikit-learn
pip install tensorboardX (only for training stage)
pip install torch==1.5.0+cu101 torchvision==0.6.0+cu101 -f https://download.pytorch.org/whl/torch_stable.html
cd ./Pointfilter/Customer_Module/chamfer_distance
python setup.py install
```

## 数据
把待测数据放在Dataset文件夹里面


## 训练
``` bash
cd Pointfilter
python train.py
```

## 测试
注意替换名称
``` bash
cd Pointfilter
python test.py --eval_dir ./Summary/pre_train_model
```

