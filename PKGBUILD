# Maintainer: Dan Johansen <strit@manjaro.org>

pkgname=qmlkonsole-git
_pkgname=qmlkonsole
pkgver=0_git20190224
pkgrel=1
_commit=eac8318020e3881dac6d930fefd278b1f4a98617
pkgdesc="Terminal app for Plasma Mobile"
arch=('aarch64')
url="https://invent.kde.org/jbbgameich/$_pkgname"
license=('GPL3')
depends=('qmltermwidget')
makedepends=('extra-cmake-modules' 'qt5-base' 'qt5-declarative' 'qt5-svg' 'qt5-quickcontrols2')
source=("https://invent.kde.org/jbbgameich/$_pkgname/-/archive/$_commit/$_pkgname-$_commit.tar.gz")
sha256sums=('e00855b09de08bc9b2826d85dc30a41374f82b1e629852146922c44b8cb7cb85')

build() {
  mkdir -p build
  cd build
  cmake ../$_pkgname-$_commit \
      -DCMAKE_BUILD_TYPE=RelWithDebInfo \
      -DCMAKE_INSTALL_PREFIX=/usr \
      -DCMAKE_INSTALL_LIBDIR=lib
  make

}

package() {
  cd build
	DESTDIR="$pkgdir" make install

} 
