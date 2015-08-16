# $Id: PKGBUILD 87653 2010-08-17 13:59:51Z jgc $
# Contributor: Michael Pusterhofer <pusterhofer@student.tugraz.at>
# Contributor: Eric Belanger <eric@archlinux.org>
# Contributor: Jan de Groot <jgc@archlinux.org>
# Maintainer: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=intltool-latest
_pkgname=intltool
pkgver=0.50.0
pkgrel=1
pkgdesc="The internationalization tool collection"
arch=('any')
url="https://edge.launchpad.net/intltool"
license=('GPL')
depends=('perl-xml-parser')
provides=('intltool=0.50.0')
conflicts=('intltool')
source=(http://edge.launchpad.net/intltool/trunk/${pkgver}/+download/${_pkgname}-${pkgver}.tar.gz)
md5sums=('0da9847a60391ca653df35123b1f7cc0')
sha1sums=('b842d3b5f4de74371049cc366dee19083061c51a')

build() {
	cd "${srcdir}/${_pkgname}-${pkgver}"
	./configure --prefix=/usr
	make
}

check() {
	cd "${srcdir}/${_pkgname}-${pkgver}"
	make check
}
    
package() {
	cd "${srcdir}/${_pkgname}-${pkgver}"
	
	make DESTDIR="${pkgdir}" install
	install -Dm644 doc/I18N-HOWTO "${pkgdir}/usr/share/doc/${_pkgname}/I18N-HOWTO"
}
