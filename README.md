# Score-Based Point Cloud Denoising-ICCV2021
源代码：https://github.com/luost26/score-denoise

## 环境配置
```bash
conda env create -f env.yml
conda activate score-denoise
```

## 数据
将待测数据放在data文件夹里

## 训练
```bash
python train.py
```

## 测试
注意替换掉名称
```bash
# PUNet dataset, 10K Points
python test.py --dataset PUNet --resolution 10000_poisson --noise 0.01 --niters 1
python test.py --dataset PUNet --resolution 10000_poisson --noise 0.02 --niters 1
python test.py --dataset PUNet --resolution 10000_poisson --noise 0.03 --niters 2
# PUNet dataset, 50K Points
python test.py --dataset PUNet --resolution 50000_poisson --noise 0.01 --niters 1
python test.py --dataset PUNet --resolution 50000_poisson --noise 0.02 --niters 1
python test.py --dataset PUNet --resolution 50000_poisson --noise 0.03 --niters 2
```







