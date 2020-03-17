# Maintainer: Dan Johansen <strit@manjaro.org>

pkgname=qmlkonsole-git
pkgver=r17.2a91881
pkgrel=1
pkgdesc="Terminal app for Plasma Mobile"
arch=('aarch64')
url="https://invent.kde.org/jbbgameich/qmlkonsole.git"
license=('GPL3')
depends=('qmltermwidget' 'kirigami2' 'ki18n')
makedepends=('git' 'extra-cmake-modules' 'qt5-base' 'qt5-declarative' 'qt5-svg' 'qt5-quickcontrols2')
source=("git+https://invent.kde.org/jbbgameich/qmlkonsole.git")
sha256sums=('SKIP')

_gitname=qmlkonsole

pkgver() {
  cd $_gitname
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  mkdir -p build
  cd build
  cmake ${srcdir}/$_gitname \
      -DCMAKE_BUILD_TYPE=RelWithDebInfo \
      -DCMAKE_INSTALL_PREFIX=/usr \
      -DCMAKE_INSTALL_LIBDIR=lib
  make

}

package() {
  cd build
	DESTDIR="$pkgdir" make install

} 
