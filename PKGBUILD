# Maintainer: Dan Johansen <strit@manjaro.org>

_pkgname=qmlkonsole
pkgname=$_pkgname-git
pkgver=r72.g50f8fb3
pkgrel=2
pkgdesc="Terminal app for Plasma Mobile"
arch=('aarch64' 'x86_64')
url="https://invent.kde.org/jbbgameich/qmlkonsole.git"
license=('GPL3')
depends=('qmltermwidget' 'kirigami2-git' 'ki18n-git')
makedepends=('git' 'extra-cmake-modules-git' 'qt5-base' 'qt5-declarative' 'qt5-svg' 'qt5-quickcontrols2')
source=("git+https://invent.kde.org/jbbgameich/qmlkonsole.git"
	"0001-Add-nano-shortcuts-to-actions.patch")
sha256sums=('SKIP'
	    '4e759d7a7d822a0a50666ecb02b98915543f81809aa95bd43e1ef5477d87e732')



pkgver() {
  cd $_pkgname
  printf "r%s.g%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
  

}

prepare() {
  cd $_pkgname

  patch -Np1 -i "${srcdir}/0001-Add-nano-shortcuts-to-actions.patch"
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
