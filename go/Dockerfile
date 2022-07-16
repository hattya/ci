FROM debian:bullseye-slim

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

RUN apt update \
 && apt install -y --no-install-recommends \
        gcc libc6-dev \
        git mercurial \
        npm \
        ca-certificates \
        curl \
 && for v in 1.16.15 1.17.12 1.18.4; do \
        mkdir -p /usr/local/go/${v} \
     && curl -sSL "https://go.dev/dl/go${v}.linux-amd64.tar.gz" \
      | tar -zxC /usr/local/go/${v} --strip-components 1 \
  ; done \
 && apt purge -y --auto-remove \
        curl \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
COPY g /usr/local/bin

ENV GOPATH="/go"
ENV PATH="${GOPATH}/bin:${PATH}"

RUN mkdir -p ${GOPATH} \
 && chmod 777 ${GOPATH} \
 && g latest
