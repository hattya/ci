# Go

A Docker image for CI with Go.


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.21
  ```console
  $ g 1.21
  go version go1.21.13 linux/amd64
  ```

- Go 1.22
  ```console
  $ g 1.22
  go version go1.22.8 linux/amd64
  ```

- Go 1.23
  ```console
  $ g 1.23
  go version go1.23.1 linux/amd64
  ```


## Platform

- Debian 12 (bookworm)
- Go 1.21 - 1.23
- GCC
  - C
- Git
- Mercurial
- Node.js 20
  - npm
