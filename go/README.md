# Go

A Docker image for CI with Go.


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.12
  ```console
  $ g 1.12
  go version go1.12.17 linux/amd64
  ```

- Go 1.13
  ```console
  $ g 1.13
  go version go1.13.15 linux/amd64
  ```

- Go 1.14
  ```console
  $ g 1.14
  go version go1.14.9 linux/amd64
  ```

- Go 1.15
  ```console
  $ g 1.15
  go version go1.15.2 linux/amd64
  ```


## Platform

- Debian 10 (buster)
- Go 1.12 - 1.15
- GCC
  - C
- Git
- Mercurial
- Node.js 10
  - npm
