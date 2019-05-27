From ubuntu:18.04

LABEL maintainer="s0r4syl"

RUN apt update && apt upgrade -y && \
  apt install -y \
  build-essential \
  make \
  git \
  wget \
  curl \
  vim \
  gdb

RUN apt install -y \
  libssl1.0-dev zlib1g-dev libbz2-dev \
  libreadline-dev libsqlite3-dev llvm libncurses5-dev libncursesw5-dev \
  xz-utils tk-dev libffi-dev liblzma-dev python-openssl libedit-dev
  
RUN git clone https://github.com/s0r4syl/ctf-tools.git ~/ctf-tools \
  && git clone https://github.com/anyenv/anyenv.git ~/.anyenv \
  && export PYENV_ROOT=~/.anyenv/envs/pyenv \
  && curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash


RUN echo \
"""
if [ -d ~/ctf-tools ]; then
    PATH=~/ctf-tools/bin:$PATH
fi
""" >> ~/.bashrc

RUN echo \
"""
if [ -d ~/.anyenv ]; then
    PATH=~/anyenv/bin:$PATH
    eval "$(anyenv init -)"
fi
""" >> ~/.bashrc
