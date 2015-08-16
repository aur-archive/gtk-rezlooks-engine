# $Id: PKGBUILD 55454 2011-09-13 00:07:49Z ebelanger $
# Contributor: Javier "Phrodo_00" Aravena <phrodo.00@gmail.com>
# Maintainer: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=gtk-rezlooks-engine
pkgver=0.6
pkgrel=11
pkgdesc="Clean looking gtk theme engine based on the cairo-enabled CVS clearlooks engine code."
arch=('i686' 'x86_64')
url="http://www.gnome-look.org/content/show.php?content=39179"
license=('GPL')
depends=('gtk2')
options=('!libtool')
source=(http://gnome-look.org/CONTENT/content-files/39179-rezlooks-$pkgver.tar.gz)
md5sums=('87b768eb372dd5065f9e36bf10245ac7')

build() {
	cd "${srcdir}/rezlooks-${pkgver}"

	./configure --prefix=/usr --enable-animation
	sed 's/glib\/gtimer/glib/g' -i src/animation.c
	make
}

package() {
	cd "${srcdir}/rezlooks-${pkgver}"

	make DESTDIR="${pkgdir}" install
	install -d "${pkgdir}/usr/share/themes"
}
