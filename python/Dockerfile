FROM ubuntu:18.04

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

RUN apt update \
 && apt install -y --no-install-recommends \
        g++ gcc lcov \
        bzr fossil git mercurial subversion \
        software-properties-common \
 && apt-add-repository -y ppa:deadsnakes/ppa \
 && apt install -y --no-install-recommends \
        python-pip python-setuptools python-wheel \
        python2.7-dev \
        python3.5-dev python3.5-venv \
        python3.6-dev python3.6-venv \
        python3.7-dev python3.7-venv \
        python3.8-dev python3.8-venv \
 && apt purge -y --auto-remove software-properties-common \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
RUN pip install -U \
        coverage \
        tox tox-venv \
 && rm -rf /root/.cache
