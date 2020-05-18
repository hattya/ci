FROM debian:buster-slim

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

RUN echo "deb http://deb.debian.org/debian buster-backports main" >> /etc/apt/sources.list \
 && apt update \
 && apt install -yt buster-backports --no-install-recommends \
        gcc libc6-dev \
        git mercurial \
        npm \
        ca-certificates \
        curl \
 && for v in 1.12.17 1.13.11 1.14.3; do \
        mkdir -p /usr/local/go/${v} \
     && curl -sSL "https://golang.org/dl/go${v}.linux-amd64.tar.gz" \
      | tar -zxC /usr/local/go/${v} --strip-components 1 \
  ; done \
 && apt purge -y --auto-remove curl \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
COPY g /usr/local/bin

ENV GOPATH="/go"
ENV PATH="${GOPATH}/bin:${PATH}"

RUN mkdir -p ${GOPATH} \
 && chmod 777 ${GOPATH} \
 && g latest

# workaround for https://bugs.debian.org/960283
RUN sed -i "/pathArray/s/ay//" /usr/lib/nodejs/dot-prop/index.js
