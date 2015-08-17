# Maintainer: Jaroslav Lichtblau <dragonlord@aur.archlinux.org>
# Contributor: Patrik Hautala <phloyd@iki.fi>

pkgname=renameutils
pkgver=0.12.0
pkgrel=1
pkgdesc="A set of programs designed to make renaming of files faster and less cumbersome"
arch=('i686' 'x86_64')
url="http://www.nongnu.org/renameutils/"
license=('GPL')
depends=('readline')
source=(http://savannah.nongnu.org/download/$pkgname/$pkgname-$pkgver.tar.gz)
sha256sums=('cbd2f002027ccf5a923135c3f529c6d17fabbca7d85506a394ca37694a9eb4a3')

build() {
  cd ${srcdir}/$pkgname-$pkgver/src
  sed -i 's/($bindir)/$(bindir)/' Makefile.am 
  sed -i 's/($bindir)/$(bindir)/' Makefile.in 

  cd ${srcdir}/$pkgname-$pkgver

  ./configure --prefix=/usr
  make
}

package () {
  cd ${srcdir}/$pkgname-$pkgver

  install -d ${pkgdir}/usr/bin
  make DESTDIR=${pkgdir} install
}
