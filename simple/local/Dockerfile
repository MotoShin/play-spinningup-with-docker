# docker image
FROM python:3.6

# Self Setting
## apt-get
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends libopenmpi-dev \
    xvfb

## python setting
RUN pip3 install --upgrade pip
RUN pip3 install --upgrade setuptools

## install jupyter lab
RUN sudo pip3 install jupyterlab
### install package for runnning gym on jupyter
COPY ../../requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
   && rm -rf /tmp/pip-tmp
RUN python -m pip install pyvirtualdisplay

# spinningup
RUN git clone https://github.com/openai/spinningup.git
WORKDIR /spinningup
RUN pip3 install -e .
