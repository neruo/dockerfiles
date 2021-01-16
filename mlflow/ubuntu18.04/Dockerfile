### build
# $ docker build -t ${user}/mlflow:ubuntu18.04 .
### run
# $ docker run -it -p 5000:5000 --name mlflow --restart always ${user}/mlflow:ubuntu18.04 /bin/bash

FROM ubuntu:18.04

### init setting
ENV DEBIAN_FRONTEND=noninteractive
RUN set -x \
 && apt-get update && apt-get upgrade -y \
 && apt-get install -y --no-install-recommends \
    tzdata \
    language-pack-ja \
    curl \
    ca-certificates \
    neovim \
 && update-locale LANG=ja_JP.UTF-8 \
 && apt-get -y clean \
 && rm -rf /var/lib/apt/lists/*
ENV TZ Asia/Tokyo
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8

### install python 3.7.9 (pyenv)
RUN set -x \
 && apt-get update \
 && apt-get install -y --no-install-recommends\
    build-essential \
    libffi-dev \
    libssl-dev \
    zlib1g-dev \
    liblzma-dev \
    libbz2-dev \
    libreadline-dev \
    libsqlite3-dev \
    git \
 && apt-get -y clean \
 && rm -rf /var/lib/apt/lists/* \
 && git clone https://github.com/pyenv/pyenv.git ~/.pyenv \
 && echo '\n##### pyenv' >> ~/.bashrc \
 && echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc \
 && echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc \
 && echo 'eval "$(pyenv init -)"' >> ~/.bashrc \
 && echo '#####\n' >> ~/.bashrc \
 && . ~/.bashrc \
 && pyenv install 3.7.9 \
 && pyenv local 3.7.9 \
 && pip install -U pip setuptools

### install mlflow
RUN set -x \
 && . ~/.bashrc \
 && pip install mlflow

