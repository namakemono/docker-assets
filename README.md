# Docker Assets

GPU版のDockerイメージ(Kaggleや実験用)

- Tensorflow 2.0.0
- fastai 1.0.59

## 検証環境

- NVIDIA-SMI 430.50
- Driver Version: 430.50
- CUDA Version: 10.1

## Tensorflow 2.0.0(GPU)

- CUDA: 10.0
- CuDNN: 7.0

### ビルド方法

```bash
docker build -t tf2-gpu:2.0.0 ./tf2-gpu-2.0.0
```

### 実行方法

```bash
NAME=XXXX
PORT=5656
sudo docker run -it --rm --name=$NAME --runtime=nvidia -v `pwd`:/kaggle -w="/kaggle/notebook" -p $PORT:8888 tf2-gpu:2.0.0 
```

## Fast.AI(GPU)

### ビルド方法

```
docker build -t fast.ai:1.0.59 ./fast-ai-1.0.59
```

### 実行方法

```bash
NAME=XXXX
PORT=5757
sudo docker run -it --rm --name=$NAME --runtime=nvidia -v `pwd`:/kaggle -w="/kaggle/notebook" -p $PORT:8888 fast.ai:1.0.59
```
