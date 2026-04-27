# StraightPCF-CVPR 2024
源代码：https://github.com/ddsediri/StraightPCF

## 环境配置
```
conda create -n StraightPCF python=3.9
conda activate StraightPCF
conda install pytorch==2.0.1 torchvision==0.15.2 torchaudio==2.0.2 pytorch-cuda=11.8 -c pytorch -c nvidia
conda install -c fvcore -c iopath -c conda-forge fvcore iopath
conda install -c bottler nvidiacub
conda install pytorch3d -c pytorch3d
pip install "git+https://github.com/facebookresearch/pytorch3d.git"
conda install pyg -c pyg
pip install point-cloud-utils==0.29.6
pip install plyfile
pip install pandas
pip install tensorboard
pip install torchsummary
conda install pytorch-cluster -c pyg
```

## 数据
将待测数据放在data文件夹下

## 训练
先单独训练VM模块:
```
python train_vm.py --val_freq=5000 --train_cvm_network=False --feat_embedding_dim=256 --decoder_hidden_dim=64
```
再从上次训练的ckpt继续训练耦合VM模块
```
python train_cvm.py --val_freq=5000 --train_cvm_network=True
```
最后训练距离模块
```
python train_straightpcf.py --val_freq=2000 --train_cvm_network=True --feat_embedding_dim=128 --decoder_hidden_dim=64
```

## 测试
注意替换名称
```
python test_straightpcf.py --niters=1 --seed_k=6 --seed_k_alpha=1 --dataset='PUNet' --resolution='10000_poisson' --noise='0.01'
```


