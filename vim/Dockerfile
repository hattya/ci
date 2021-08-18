FROM debian:buster-slim

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

ARG VIM74="v7.4.280"
ARG VIM80="v8.0.0002"
ARG VIM81="v8.1.0001"
ARG VIM82="v8.2.0000"

RUN echo "deb http://deb.debian.org/debian buster-backports main" >> /etc/apt/sources.list.d/backports.list \
 && printf "Package: libcurl3-gnutls\nPin: release o=Debian, n=buster\nPin-Priority: 1001\n" >> /etc/apt/preferences.d/curl \
 && apt update \
 && apt install -yt buster-backports --no-install-recommends \
        gcc make \
        libacl1-dev libncurses-dev\
        brz cvs fossil git mercurial subversion \
        ca-certificates \
        python3-pip python3-setuptools python3-wheel \
 && git clone -q https://github.com/vim/vim /tmp/vim \
 && cd /tmp/vim \
 && for v in ${VIM74} ${VIM80} ${VIM81} ${VIM82}; do \
        git checkout -q ${v} \
     && ./configure \
            --prefix=/usr/local/vim/$(git describe --tags | cut -c2-) \
            --with-features=huge \
            --enable-fail-if-missing \
     && make install \
  ; done \
 && cd - >/dev/null \
 && rm -rf /tmp/vim \
 && apt purge -y --auto-remove \
        gcc make \
        libacl1-dev libncurses-dev \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
COPY v /usr/local/bin

ARG LATEST="v8.2.3310"

RUN apt update \
 && apt install -yt buster-backports --no-install-recommends \
        gcc make \
        libacl1-dev libncurses-dev\
 && git -c advice.detachedHead=false clone -q -b ${LATEST} --depth 1 https://github.com/vim/vim /tmp/vim \
 && cd /tmp/vim \
 && ./configure \
        --prefix=/usr/local/vim/$(git describe --tags | cut -c2-) \
        --with-features=huge \
        --enable-fail-if-missing \
 && make install \
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
 && pip3 install -U "click<8" covimerage \
 && rm -rf /root/.cache
