# Vim

A Docker image for CI with Vim.


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

- Vim 9.0
  ```console
  $ v 9.0
  Vim 9.0
  ```

- Vim 9.1
  ```console
  $ v 9.1
  Vim 9.1
  ```

- Vim latest
  ```console
  $ v latest
  Vim 9.1.400
  ```


## Platform

- Debian 12 (bookworm)
- Vim 7.4 - 9.1, latest
  - themis.vim
- Python 3.11
  - Primula
- Breezy
- CVS
- Darcs
- Fossil
- Git
- Mercurial
- Subversion


## Build-Time Variables

- `VIM74`:  A version of Vim 7.4.
- `VIM80`:  A version of Vim 8.0.
- `VIM81`:  A version of Vim 8.1.
- `VIM82`:  A version of Vim 8.2.
- `VIM90`:  A version of Vim 9.0.
- `VIM91`:  A version of Vim 9.1.
- `LATEST`: The latest version of Vim.
