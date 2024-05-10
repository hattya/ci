FROM debian:bookworm-slim

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

RUN apt update \
 && apt install -y --no-install-recommends \
        gcc libc6-dev \
        git mercurial \
        ca-certificates \
        curl \
 && for v in 1.20.14 1.21.10 1.22.3; do \
        mkdir -p /usr/local/go/${v} \
     && curl -sSL https://go.dev/dl/go${v}.linux-amd64.tar.gz \
      | tar -zxC /usr/local/go/${v} --strip-components 1 \
  ; done \
 && curl -sSL https://deb.nodesource.com/setup_lts.x | bash - \
 && apt install -y --no-install-recommends \
        nodejs \
 && apt purge -y --auto-remove \
        curl \
        lsb-release gnupg \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
COPY g /usr/local/bin

ENV GOPATH="/go"
ENV PATH="${GOPATH}/bin:${PATH}"

RUN mkdir -p ${GOPATH} \
 && chmod 777 ${GOPATH} \
 && g latest
