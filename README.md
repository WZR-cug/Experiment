# PD-Flow-ECCV2022
源代码：https://github.com/unknownue/pdflow

## 环境配置
```bash
conda create -n PDFlow python=3.8
conda install pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch
conda install lightning=1.5.4 -c conda-forge
pip install --upgrade https://github.com/unlimblue/KNN_CUDA/releases/download/0.2/KNN_CUDA-0.2-py3-none-any.whl
pip install point-cloud-utils==0.31.0
conda install pytorch3d::pytorch3d
pip install torch-cluster -f https://data.pyg.org/whl/torch-1.11.0+cu113.html
pip install kaolin==0.18.0 -f https://nvidia-kaolin.s3.us-east-2.amazonaws.com/torch-1.11.0_cu113.html
cd metric/PytorchEMD/
python setup.py install --user
cp build/lib.linux-x86_64-3.8/emd_cuda.cpython-38m-x86_64-linux-gnu.so .
```

## 数据
将待测数据放在data文件夹下

## 训练
```bash
python models/deflow/train_deflow_score.py
```

## 测试
注意替换名称:
```bash
python models/deflow/denoise.py \
    --input=path/to/input_directory \
    --output=path/to/output_directory \
    --patch_size=1024 --niters=1 --ckpt=pretrain/pdflow-score-LCC.pt
```
验证
```bash
python eval/eval2.py \
    --pred_dir=path/to/evaluation/directory \
    --off_dir=path/to/off_mesh/directory \
    --gt_dir=path/to/ground_truth/directory \
    --csv=path/to/evaluation/directory/result.csv
```

