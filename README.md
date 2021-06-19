Git for Windows repository for MSYS2

This project simply provides a script replaying steps described in [Wiki](https://github.com/git-for-windows/git/wiki/Install-inside-MSYS2-proper) of [Git for Windows](https://github.com/git-for-windows/git) and an installable package for use by `pacman`

It's useful for those who work on both [MSYS2](https://www.msys2.org/) and [Git for Windows](https://gitforwindows.org/) and doesn't wanna have two or more similar environments installed on their PC.

## How to use

### Install Git for Windows

1. Configure repository

```shell
( PKGVER=20210619 PKGREL=1 PKGFILN=git-for-windows-release-${PKGVER}-${PKGREL}-any.pkg.tar.xz ; curl -L -o ${TMP}/${PKGFILN} https://github.com/ieu/msys2-git-for-windows-release/releases/download/${PKGVER}-${PKGREL}/${PKGFILN} && pacman -U --needed --noconfirm ${TMP}/${PKGFILN} ; ( [ -f ${TMP}/${PKGFILN} ] && rm ${TMP}/${PKGFILN} ) )
```

2. Synchronize repository and upgrade runtime

```shell
pacman -Syyuu
```

This will replace your `msys2-runtime` with patched one which requires terminating all MSYS2 processes and start a new MSYS2 terminal.

3. Upgrade rest as needed

```shell
pacman -Suu
```

It's expected if some packages were downgraded.

4. Install Git for Windows

```shell
pacman -S mingw-w64-x86_64-git
```

or install 32-bit version instead:

```shell
pacman -S mingw-w64-i686-git
```
