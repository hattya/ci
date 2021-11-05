# Go

A Docker image for CI with Go.

[![Docker Hub](https://img.shields.io/docker/cloud/build/hattya/go)](https://hub.docker.com/r/hattya/go)


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.15
  ```console
  $ g 1.15
  go version go1.15.15 linux/amd64
  ```

- Go 1.16
  ```console
  $ g 1.16
  go version go1.16.10 linux/amd64
  ```

- Go 1.17
  ```console
  $ g 1.17
  go version go1.17.3 linux/amd64
  ```


## Platform

- Debian 11 (bullseye)
- Go 1.15 - 1.17
- GCC
  - C
- Git
- Mercurial
- Node.js 12
  - npm
