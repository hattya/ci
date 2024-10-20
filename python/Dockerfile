FROM ubuntu:24.04

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

RUN apt update \
 && apt install -y --no-install-recommends \
        g++ gcc lcov \
        brz fossil git mercurial subversion \
        gpg-agent software-properties-common \
	cabal-install \
 && apt-add-repository -y ppa:deadsnakes/ppa \
 && apt install -y --no-install-recommends \
        python3.9-dev  python3.9-venv \
        python3.10-dev python3.10-venv \
        python3.11-dev python3.11-venv \
        python3.12-dev python3.12-venv \
        python3.13-dev python3.13-venv python3.13-nogil \
        python3-pip python3-coverage tox \
        python-dev-is-python3 \
 && ln -s /usr/bin/python3-coverage /usr/local/bin/coverage \
 && cabal update \
 && cabal install --jobs --install-method copy --installdir /usr/local/bin darcs \
 && strip -p --strip-unneeded --remove-section .comment /usr/local/bin/darcs \
 && rm -rf /root/.cabal \
 && apt purge -y --auto-remove \
        gpg-agent software-properties-common \
	cabal-install \
 && apt clean \
 && rm -rf /root/.launchpadlib /var/lib/apt/lists/*
