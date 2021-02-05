# Go

A Docker image for CI with Go.

[![Docker Hub](https://img.shields.io/docker/cloud/build/hattya/go)](https://hub.docker.com/r/hattya/go)


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.13
  ```console
  $ g 1.13
  go version go1.13.15 linux/amd64
  ```

- Go 1.14
  ```console
  $ g 1.14
  go version go1.14.15 linux/amd64
  ```

- Go 1.15
  ```console
  $ g 1.15
  go version go1.15.7 linux/amd64
  ```


## Platform

- Debian 10 (buster)
- Go 1.13 - 1.15
- GCC
  - C
- Git
- Mercurial
- Node.js 10
  - npm
