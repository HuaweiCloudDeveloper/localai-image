# Install localai

## Download dokcer image
```shell
# pull localai image
docker pull localai/localai:v3.0.0

# run localai
cd ~
mkdir -p localai/models

# start with stdio
cd ~/localai
docker run -p 8080:8080 -v $PWD/models:/models -ti --rm localai/localai:v3.0.0 --models-path /models

# start and detach
cd ~/localai
docker run -d -p 8080:8080 -v $PWD/models:/models --rm localai/localai:v3.0.0 --models-path /models
```