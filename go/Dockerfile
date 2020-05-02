FROM debian:buster-slim

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive"
ENV LANG="C.UTF-8"

RUN apt update \
 && apt install -y --no-install-recommends \
        gcc libc6-dev \
        git mercurial \
        ca-certificates \
	curl jq \
 && for v in 1.12 1.13 1.14; do \
        mkdir -p /usr/local/go/${v} \
     && curl -sS "https://golang.org/dl/?mode=json&include=all" \
      | jq -r --arg v ${v} '[.[] | select((.version | startswith("go" + $v)) and .stable)][0] | .files[] | select(.os == "linux" and .arch == "amd64") | "https://golang.org/dl/" + .filename' \
      | xargs curl -sSL \
      | tar -zxC /usr/local/go/${v} --strip-components 1 \
  ; done \
 && apt purge -y --auto-remove curl jq \
 && apt clean \
 && rm -rf /var/lib/apt/lists/*
COPY g /usr/local/bin

ENV GOPATH="/go"
ENV PATH="${GOPATH}/bin:${PATH}"

RUN mkdir -p ${GOPATH} \
 && chmod 777 ${GOPATH} \
 && g latest
