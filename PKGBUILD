# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=ktextwidgets
pkgver=4.99.0
pkgrel=1
pkgdesc='KTextWidgets'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/ktextwidgets'
license=('LGPL')
depends=('kcompletion' 'kservice' 'kiconthemes' 'sonnet')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('a8dcb0d4d24699d1507caaafefa5498e')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
