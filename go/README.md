# Go

A Docker image for CI with Go.


## Installation

```console
$ docker pull hattya/go
```


## Usage

You can use a command-line flag or an environment variable to switch versions
of Go. A command-line flag takes precedence, and the latest version is used by
default.

- Command-Line Flag
  ```console
  $ go -1.14 version
  go version go1.14.2 linux/amd64
  ```

- Environment Variable
  ```console
  $ export GO=1.14
  $ go version
  go version go1.14.2 linux/amd64
  ```


## Platform

- Debian 10 (buster)
- Go 1.12 - 1.14
- GCC
  - C
- Git
- Mercurial
