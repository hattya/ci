FROM ubuntu:22.04

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

RUN apt update \
 && apt install -y --no-install-recommends \
        g++ gcc lcov \
        brz darcs fossil git mercurial subversion \
        gpg-agent software-properties-common \
 && apt-add-repository -y ppa:deadsnakes/ppa \
 && apt install -y --no-install-recommends \
        python3.8-dev  python3.8-venv \
        python3.9-dev  python3.9-venv \
        python3.10-dev python3.10-venv \
        python3.11-dev python3.11-venv \
        python3.12-dev python3.12-venv \
        python3-pip python3-setuptools python3-wheel \
        python-dev-is-python3 \
 && apt purge -y --auto-remove \
        gpg-agent software-properties-common \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
RUN pip install -U \
        coverage \
        tox \
 && rm -rf /root/.cache
