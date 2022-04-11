# Vim

A Docker image for CI with Vim.

[![Docker Hub](https://img.shields.io/docker/cloud/build/hattya/vim)](https://hub.docker.com/r/hattya/vim)


## Installation

```console
$ docker pull hattya/vim
```


## Usage

There is `v` command to switch Vim versions.

- Vim 7.4
  ```console
  $ v 7.4
  Vim 7.4.280
  ```

- Vim 8.0
  ```console
  $ v 8.0
  Vim 8.0.2
  ```

- Vim 8.1
  ```console
  $ v 8.1
  Vim 8.1.1
  ```

- Vim 8.2
  ```console
  $ v 8.2
  Vim 8.2
  ```

- Vim latest
  ```console
  $ v latest
  Vim 8.2.4707
  ```


## Platform

- Debian 11 (bullseye)
- Vim 7.4 - 8.2, latest
  - themis.vim
- Python 3.9
  - covimerage
- Breezy
- CVS
- Fossil
- Git
- Mercurial
- Subversion


## Build-Time Variables

- `VIM74`:  A version of Vim 7.4.
- `VIM80`:  A version of Vim 8.0.
- `VIM81`:  A version of Vim 8.1.
- `VIM82`:  A version of Vim 8.2.
- `LATEST`: The latest version of Vim.
