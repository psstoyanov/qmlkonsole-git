# Maintainer: Dan Johansen <strit@manjaro.org>

_pkgname=qmlkonsole
pkgname=$_pkgname-git
pkgver=r63.3742e22
pkgrel=2
pkgdesc="Terminal app for Plasma Mobile"
arch=('aarch64' 'x86_64')
url="https://invent.kde.org/jbbgameich/qmlkonsole.git"
license=('GPL3')
depends=('qmltermwidget' 'kirigami2-git' 'ki18n-git')
makedepends=('git' 'extra-cmake-modules-git' 'qt5-base' 'qt5-declarative' 'qt5-svg' 'qt5-quickcontrols2')
source=("git+https://invent.kde.org/jbbgameich/qmlkonsole.git")
sha256sums=('SKIP')

pkgver() {
  cd $_pkgname
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  mkdir -p build
  cd build
  cmake ${srcdir}/$_pkgname \
      -DCMAKE_BUILD_TYPE=RelWithDebInfo \
      -DCMAKE_INSTALL_PREFIX=/usr \
      -DCMAKE_INSTALL_LIBDIR=lib
  make

}

package() {
  cd build
	DESTDIR="$pkgdir" make install

} 
