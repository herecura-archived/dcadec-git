# Maintainer: Maxime Gauduin <alucryd@archlinux.org>
# Contributor: Yamashita Ren <lemaitre.lotus@gmail.com>

pkgname=dcadec-git
pkgver=20150605.2a9186e
pkgrel=1
pkgdesc='DTS Coherent Acoustics decoder with support for HD extensions'
arch=('i686' 'x86_64')
url='https://github.com/foo86/dcadec.git'
license=('LGPL2.1')
depends=('glibc')
conflicts=()
provides=('dcadec')
makedepends=('git')
source=('git://github.com/foo86/dcadec.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_gitname"
  git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
  cd dcadec

  export CONFIG_SHARED='TRUE'

  make
}

package() {
  cd dcadec

  export CONFIG_SHARED='TRUE'
  export PREFIX='/usr'

  make DESTDIR="${pkgdir}" install
  mv "${pkgdir}"/usr/bin/{dcadec,dcahddec}
}

# vim: ts=2 sw=2 et:
