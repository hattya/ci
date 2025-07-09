# Go

A Docker image for CI with Go.


## Installation

```console
$ docker pull hattya/go
```


## Usage

There is `g` command to switch versions of Go.

- Go 1.22
  ```console
  $ g 1.22
  go version go1.22.12 linux/amd64
  ```

- Go 1.23
  ```console
  $ g 1.23
  go version go1.23.11 linux/amd64
  ```

- Go 1.24
  ```console
  $ g 1.24
  go version go1.24.4 linux/amd64
  ```


## Platform

- Debian 12 (bookworm)
- Go 1.22 - 1.24
- GCC
  - C
- Git
- Mercurial
- Node.js 22
  - npm
