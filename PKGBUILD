# Maintainer: anex <assassin.anex[@]gmail.com>

pkgname=trojita-qt5-git
pkgver=5713.ae51ffa
pkgrel=2
pkgdesc="A fast QT IMAP e-mail client"
arch=(i686 x86_64)
url="http://trojita.flaska.net"
license=('GPL')
depends=('qt5-webkit')
conflicts=('trojita' 'trojita-git')
provides=('trojita')
makedepends=('git' 'cmake')

source=('git://anongit.kde.org/trojita.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/trojita"
	echo $(git rev-list --count master).$(git rev-parse --short master)
}

build() {
	cd "$srcdir/trojita"
	cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release . -DWITH_QT5=ON
	make
}

package() {
	cd "$srcdir/trojita"
	make install DESTDIR="$pkgdir"
}