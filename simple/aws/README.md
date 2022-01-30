# aws実験用のDcokerfile
gpu使用可能なサーバでコンテナを作るときに使用するDockerfile

## 起動方法
```
$ docker run -it -p 8888:8888 spinningup/python:latest /bin/bash
$ jupyter lab --ip 0.0.0.0 --allow-root
```
