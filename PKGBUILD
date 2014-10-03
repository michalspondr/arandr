# Maintainer: nd0ut <nd0ut.me@gmail.com>

pkgname=arandr-git
_realname=arandr
pkgver=20141003
pkgrel=3
pkgdesc="Provide a simple visual front end for XRandR 1.2."
arch=('any')
url="http://christian.amsuess.com/tools/arandr/"
license=('GPL3')
depends=('pygtk' 'desktop-file-utils' 'xorg-xrandr')
makedepends=('docutils' 'git')
conflicts=('arandr')
provides=('arandr')
install=$pkgname.install

source=(git://github.com/nd0ut/arandr.git)
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/${_realname}"
  git log -1 --format="%cd" --date=short | tr -d '-'
}

build() {
  cd "$srcdir/${_realname}"
  python2 setup.py build
}

package() {
  cd "$srcdir/${_realname}"
  python2 setup.py install --prefix=/usr --root="$pkgdir" --optimize=1
}

