# local検証用のDcokerfile
vscodeのRemote-Containerの機能を使用しての開発環境構築ではなく素のdockerを使っての検証環境構築に使用するDockerfile

## 起動方法
```
$ docker run -it -p 8888:8888 spinningup/python:latest /bin/bash
$ jupyter lab --ip 0.0.0.0 --allow-root
```
