# docker image
FROM nvidia/cuda:11.6.0-runtime-ubuntu18.04

# Self Setting
## apt-get
RUN apt-get update \
    && apt-get -y install --no-install-recommends libopenmpi-dev \
    python3 \
    python3-pip \
    python3-opengl \
    build-essential \
    git \
    xvfb

## python setting
RUN pip3 install --upgrade pip
RUN pip3 install --upgrade setuptools

## install jupyter lab
RUN pip3 install jupyterlab
### install package for runnning gym on jupyter
COPY requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
   && rm -rf /tmp/pip-tmp
RUN python3 -m pip install pyvirtualdisplay

# spinningup
RUN git clone https://github.com/openai/spinningup.git
WORKDIR /spinningup
RUN pip3 install -e .
WORKDIR /
RUN rm -rf /spinningup

# 作業ディレクトリに移動
RUN mkdir workspace
WORKDIR /workspace
