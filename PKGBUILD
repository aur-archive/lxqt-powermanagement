# Contributor: Antonio Rojas

pkgname=lxqt-powermanagement
pkgver=0.8.0
pkgrel=2
pkgdesc="Daemon use for power management and auto-suspend"
arch=('i686' 'x86_64')
url='http://lxqt.org/'
license=('LGPL')
groups=('lxqt')
depends=('liblxqt' 'qt5-svg' 'upower' 'hicolor-icon-theme')
makedepends=('cmake' 'qt5-tools')
source=("http://lxqt.org/downloads/lxqt/$pkgver/$pkgname-$pkgver.tar.xz")
md5sums=('3dfb506a077a36b822389f4679c824c9')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DUSE_QT5=ON
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
