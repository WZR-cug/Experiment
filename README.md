# P2P-Bridge-ECCV2024
源代码：https://github.com/matvogel/P2P-Bridge

## 环境配置
```bash
conda create -n p2pb python=3.10
conda activate p2pb
conda install pytorch==2.1.2 torchvision==0.16.2 pytorch-cuda=11.8 -c pytorch -c nvidia --yes
sh install.sh
pip install -r requirements_data.txt
```	

## 数据
将待测数据放在data/objects文件夹下

## 训练
注意替换名称
```bash
python train.py --save_dir <SAVE DIRECTORY> 
```

## 测试
注意替换名称
```bash
python evaluate_objects.py --model_path ./pretrained/PVDS_PUNet/latest.pth --dataset PUNet
python evaluate_objects.py --model_path ./pretrained/PVDS_PUNet/latest.pth --dataset PCNet
python evaluate_objects.py --help
```

