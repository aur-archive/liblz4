# Maintainer: SneakySnake <radiantstatue@gmail.com>
# Submit issues/pull requests at https://github.com/crumblingstatue/pkgbuilds

pkgname=liblz4
pkgver=110
pkgrel=1
pkgdesc='Very fast lossless compression algorithm (development files)'
arch=('i686' 'x86_64')
url='https://code.google.com/p/lz4/'
license=('GPL2')
makedepends=('svn' 'cmake')
depends=('glibc')
source=("$pkgname::svn+http://lz4.googlecode.com/svn/trunk/#revision=$pkgver")
md5sums=('SKIP')

build() {
  cd "$pkgname/cmake"
  cmake -DBUILD_LIBS=ON \
        -DBUILD_TOOLS=OFF \
        -DBUILD_SHARED_LIBS=ON \
        -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "$srcdir/$pkgname/cmake"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
