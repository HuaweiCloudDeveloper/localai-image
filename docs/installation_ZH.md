# 安装LocalAI

## 下载Docker镜像
```shell
# 拉取localai镜像
docker pull localai/localai:v3.0.0

# 运行localai
cd ~
mkdir -p localai/models

# 以标准IO模式启动
cd ~/localai
docker run -p 8080:8080 -v $PWD/models:/models -ti --rm localai/localai:v3.0.0 --models-path /models

# 以守护进程模式启动
cd ~/localai
docker run -d -p 8080:8080 -v $PWD/models:/models --rm localai/localai:v3.0.0 --models-path /models
```