PKGEXT='.pkg.tar.xz'
pkgname=git-for-windows-release
pkgver=20210619
pkgrel=1
pkgdesc='Git for Windows release for MSYS2'
arch=('any')
url='https://github.com/ieu/msys2-git-for-windows-release'
license=('GPL')
depends=('git-for-windows-keyring')
install="${pkgname}.install"
source=(mirrorlist.git-for-windows-mingw32
        mirrorlist.git-for-windows-mingw64)
sha256sums=('63e416fa6e385067529a194f46f43b0c80c810c8cdbca592d2750aee0a1463e4'
            'e3a618d9708acd4ed224f82ae0e8dc1e366f99f190cc9bf9c935862dafb4fa62')

package() {
  mkdir -p ${pkgdir}/etc/pacman.d
  install -m644 ${srcdir}/mirrorlist.git-for-windows-mingw32 ${pkgdir}/etc/pacman.d/
  install -m644 ${srcdir}/mirrorlist.git-for-windows-mingw64 ${pkgdir}/etc/pacman.d/
}
