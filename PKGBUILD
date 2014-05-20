# Maintainer: Zachary Michaels
pkgname=vranger-git
pkgrel=1
pkgver=1.0.r31.gf20ab06
pkgdesc="vim/ranger integration scripts"
arch=('i686' 'x86_64')
url="http://github.com/mikezackles/vranger"
depends=('tmux' 'ranger' 'vim')
provides=('vranger')
conflicts=('vranger')
license=('GPL')
source=('vranger' 'vrim')
md5sums=(SKIP SKIP)

pkgver() {
  #cd "$srcdir/vranger"
  git describe --long --tags | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

package() {
  install -Dm755 "$startdir/vranger" "$pkgdir/usr/bin/vranger"
  install -Dm755 "$startdir/vrim" "$pkgdir/usr/bin/vrim"
}
