# Go

A Docker image for CI with Go.


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.23
  ```console
  $ g 1.23
  go version go1.23.12 linux/amd64
  ```

- Go 1.24
  ```console
  $ g 1.24
  go version go1.24.13 linux/amd64
  ```

- Go 1.25
  ```console
  $ g 1.25
  go version go1.25.6 linux/amd64
  ```


## Platform

- Debian 13 (trixie)
- Go 1.23 - 1.25
- GCC
  - C
- Git
- Mercurial
- Node.js 24
  - npm
