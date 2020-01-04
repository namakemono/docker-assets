# Docker Assets

機械学習関連のDockerイメージ

## Tensorflow 2.0.0(GPU版)

- CUDA: 10.0
- CuDNN: 7.0

### ビルド方法

```bash
docker build -t tf2-gpu:2.0.0 ./tf2-gpu-2.0.0
```

### 実行方法

```bash
sudo docker run -it --rm --name="tf2qa" --runtime=nvidia -v `pwd`:/kaggle -w="/kaggle/notebook" -p  5656:8888 tf2-gpu:2.0.0 
```

