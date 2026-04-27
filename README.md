# DMR-ACM MM2020
源代码：https://github.com/luost26/DMRDenoise

## 环境配置
```bash
conda env create -f environment.yml
conda activate DMRDenoise
cd ./ops/emd
python setup.py install
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

