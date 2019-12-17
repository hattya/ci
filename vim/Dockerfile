FROM alpine:3.10

LABEL maintainer="Akinori Hattori <hattya@gmail.com>"

ARG VIM74="v7.4.280"
ARG VIM80="v8.0.0002"
ARG VIM81="v8.1.0001"
ARG VIM82="v8.2.0000"

RUN apk add --no-cache \
        acl ncurses \
        bzr cvs fossil git mercurial subversion \
        python3 \
 && apk add --no-cache --virtual .build \
        gcc make \
        acl-dev libc-dev ncurses-dev \
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
 && apk del --purge .build
COPY v /usr/local/bin

ARG LATEST="v8.2.0014"

RUN apk add --no-cache --virtual .build \
        gcc make \
        acl-dev libc-dev ncurses-dev \
 && git -c advice.detachedHead=false clone -q -b ${LATEST} --depth 1 https://github.com/vim/vim /tmp/vim \
 && cd /tmp/vim \
 && ./configure \
        --prefix=/usr/local/vim/$(git describe --tags | cut -c2-) \
        --with-features=huge \
        --enable-fail-if-missing \
 && make install \
 && cd - >/dev/null \
 && rm -rf /tmp/vim \
 && apk del --purge .build \
 && v latest
RUN git clone --depth 1 https://github.com/thinca/vim-themis /opt/themis \
 && rm -rf /opt/themis/.git \
 && ln -s ../../../opt/themis/bin/themis /usr/local/bin/themis \
 && pip3 install -U covimerage \
 && rm -rf /root/.cache
