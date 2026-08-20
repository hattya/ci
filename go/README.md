# Go

A Docker image for CI with Go.


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.24
  ```console
  $ g 1.24
  go version go1.24.13 linux/amd64
  ```

- Go 1.25
  ```console
  $ g 1.25
  go version go1.25.14 linux/amd64
  ```

- Go 1.26
  ```console
  $ g 1.26
  go version go1.26.7 linux/amd64
  ```

- Go 1.27
  ```console
  $ g 1.27
  go version go1.27.0 linux/amd64
  ```


## Platform

- Debian 13 (trixie)
- Go 1.24 - 1.27
- GCC
  - C
- Git
- Mercurial
- Node.js 24
  - npm
