# Go

A Docker image for CI with Go.


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.19
  ```console
  $ g 1.19
  go version go1.19.12 linux/amd64
  ```

- Go 1.20
  ```console
  $ g 1.20
  go version go1.20.13 linux/amd64
  ```

- Go 1.21
  ```console
  $ g 1.21
  go version go1.21.6 linux/amd64
  ```


## Platform

- Debian 12 (bookworm)
- Go 1.19 - 1.21
- GCC
  - C
- Git
- Mercurial
- Node.js 18
  - npm
