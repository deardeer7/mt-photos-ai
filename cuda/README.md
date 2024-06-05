# 安装说明（GPU版）

- CLIP使用PyTorch，PaddleOCR使用PaddlePaddle。
- 使用同一个python环境，安装CLIP和PaddleOCR，出现兼容性问题，故分开安装。

## CLIP

### 创建虚拟环境

```bash
conda create -n clip python=3.10.0
conda activate clip
```

### 安装 PyTorch

参考[安装说明](https://pytorch.org/get-started/locally/)选择合适的版本安装。

这里以 CUDA 11.8 Pytorch 2.0.0 为例：

```bash
pip install torch==2.0.0+cu118 torchvision==0.15.1+cu118 torchaudio==2.0.1+cu118 -f https://download.pytorch.org/whl/torch_stable.html
```

### 安装依赖

```bash
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
pip install -r requirements.txt
```

### 测试

```bash
python
>>> import torch
>>> torch.cuda.is_available()
True
```

### 运行

```bash
python server-clip.py
```

## PaddleOCR

### 创建虚拟环境

```bash
conda create -n ocr python=3.10.0
conda activate ocr
```

### 安装 PaddlePaddle-GPU

参考[安装说明](https://www.paddlepaddle.org.cn/install/quick?docurl=/documentation/docs/zh/install/pip/windows-pip.html)选择合适版本安装。

这里以 CUDA 11.8 PaddlePaddle 2.6.1 为例：

```bash
python -m pip install paddlepaddle-gpu==2.6.1 -i https://pypi.tuna.tsinghua.edu.cn/simple
```

### 安装依赖

```bash
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
pip install -r requirements-ocr.txt
```

### 测试

```bash
python
>>> import paddle
>>> paddle.utils.run_check()
```

### 运行

```bash
python server-ocr.py
```
