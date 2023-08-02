# Go

A Docker image for CI with Go.

[![Docker Hub](https://img.shields.io/docker/cloud/build/hattya/go)](https://hub.docker.com/r/hattya/go)


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.18
  ```console
  $ g 1.18
  go version go1.18.10 linux/amd64
  ```

- Go 1.19
  ```console
  $ g 1.19
  go version go1.19.12 linux/amd64
  ```

- Go 1.20
  ```console
  $ g 1.20
  go version go1.20.7 linux/amd64
  ```


## Platform

- Debian 11 (bullseye)
- Go 1.18 - 1.20
- GCC
  - C
- Git
- Mercurial
- Node.js 16
  - npm
