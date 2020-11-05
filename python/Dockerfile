FROM ubuntu:20.04

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

RUN apt update \
 && apt install -y --no-install-recommends \
        g++ gcc lcov \
        brz fossil git mercurial subversion \
        software-properties-common \
 && apt-add-repository -y ppa:deadsnakes/ppa \
 && apt install -y --no-install-recommends \
        python2.7-dev \
        python3.6-dev python3.6-venv \
        python3.7-dev python3.7-venv \
        python3.8-dev python3.8-venv \
        python3.9-dev python3.9-venv \
        python3-pip python3-setuptools python3-wheel \
 && apt purge -y --auto-remove software-properties-common \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
RUN pip3 install -U \
         coverage \
         tox tox-venv \
 && rm -rf /root/.cache

# workaround for Python 3.6
RUN sed -i "s/-specs=.*\.specs *//" /usr/lib/python3.6/_sysconfigdata*.py
