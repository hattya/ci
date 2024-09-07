FROM debian:bookworm-slim

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

ARG VIM74="v7.4.280"
ARG VIM80="v8.0.0002"
ARG VIM81="v8.1.0001"
ARG VIM82="v8.2.0000"
ARG VIM90="v9.0.0000"
ARG VIM91="v9.1.0000"

RUN apt update \
 && apt install -y --no-install-recommends \
        gcc make \
        libacl1-dev libncurses-dev\
        brz cvs darcs fossil git mercurial subversion \
        python3-venv \
        python-is-python3 \
 && git clone -q https://github.com/vim/vim /tmp/vim \
 && cd /tmp/vim \
 && for v in ${VIM74} ${VIM80} ${VIM81} ${VIM82} ${VIM90} ${VIM91}; do \
        git checkout -q ${v} \
     && ./configure \
            --prefix=/usr/local/vim/$(git describe --tags | cut -c 2-) \
            --with-features=huge \
            --enable-fail-if-missing \
     && make -j $(nproc) install \
  ; done \
 && cd - >/dev/null \
 && rm -rf /tmp/vim \
 && apt purge -y --auto-remove \
        gcc make \
        libacl1-dev libncurses-dev \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
COPY v /usr/local/bin

ARG LATEST="v9.1.0702"

RUN apt update \
 && apt install -y --no-install-recommends \
        gcc make \
        libacl1-dev libncurses-dev\
 && git -c advice.detachedHead=false clone -q -b ${LATEST} --depth 1 https://github.com/vim/vim /tmp/vim \
 && cd /tmp/vim \
 && ./configure \
        --prefix=/usr/local/vim/$(git describe --tags | cut -c 2-) \
        --with-features=huge \
        --enable-fail-if-missing \
 && make -j $(nproc) install \
 && cd - >/dev/null \
 && rm -rf /tmp/vim \
 && apt purge -y --auto-remove \
        gcc make \
        libacl1-dev libncurses-dev \
 && apt clean \
 && rm -rf /var/lib/apt/lists/* \
 && v latest
RUN git clone --depth 1 https://github.com/thinca/vim-themis /opt/themis \
 && rm -rf /opt/themis/.git \
 && ln -s ../../../opt/themis/bin/themis /usr/local/bin/themis \
 && python -m venv /opt/primula \
 && /opt/primula/bin/python -m pip install -U pip \
 && /opt/primula/bin/python -m pip install -U primula==0.4 \
 && ln -s ../../../opt/primula/bin/primula /usr/local/bin/primula
