# Maintainer: Andras Biro <bbandi86@gmail.com>
pkgname=nesc
pkgver=1.3.6
pkgrel=2
pkgdesc="A C dialect developed for TinyOS"
arch=('i686' 'x86_64')
license=('GPL')
options=(!libtool !buildflags)
url="http://nescc.sourceforge.net/"
depends=('perl' 'java-environment' 'gperf')
source=("https://github.com/tinyos/${pkgname}/archive/v${pkgver}.tar.gz")
sha1sums=('27b316fb709135f0d383cbf969419e561197a018')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./Bootstrap
  ./configure --prefix=/usr/
  make || return 1
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR="$pkgdir/" install || return 1
}
