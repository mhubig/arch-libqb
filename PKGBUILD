#Maintainer: ovi chis <ovi@ovios.org>
#Contributor Tim Meusel <tim@bastelfreak.de>

pkgname=libqb
pkgver=0.17.2
pkgrel=1
pkgdesc="Library with the primary purpose of providing high performance client server reusable features"
arch=("i686" "x86_64" "mips64el")
url="https://github.com/ClusterLabs/$pkgname/wiki"
license=("LGPL2.1")

makedepends=(
  doxygen
  splint
)

options=(!libtool)

source=("https://github.com/ClusterLabs/$pkgname/releases/download/v$pkgver/$pkgname-$pkgver.tar.xz")
sha512sums=("9c6dce7d18aa4da31594faecd0ea2737c2beefa749290094f733fe89ac40f094ec6409f310c534b8144d500e8c204c328386eaf1029995698d7019c014433443")

build() {
    cd $srcdir/$pkgname-$pkgver
    setarch $CARCH ./configure --prefix=/usr\
        --disable-static\
        --libdir=/usr/lib\
        --sbindir=/usr/bin
    setarch $CARCH make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    setarch $CARCH make DESTDIR=$pkgdir install
}
