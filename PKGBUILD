# $Id$
# Maintainer: Jaroslav Lichtblau <dragonlord@aur.archlinux.org>
# Contributor: Eric Belanger <eric@archlinux.org>
# Contributor: SmackleFunky <smacklefunky@optusnet.com.au>

pkgname=ltris
pkgver=1.0.19
pkgrel=2
pkgdesc="A tetris clone where you have a bowl with blocks falling down"
arch=('i686' 'x86_64')
url="http://lgames.sourceforge.net/index.php?project=LTris"
license=('GPL')
depends=('sdl_mixer')
backup=('var/games/ltris.hscr')
install=$pkgname.install
changelog=$pkgname.changelog
source=(http://downloads.sourceforge.net/lgames/$pkgname-$pkgver.tar.gz)
sha256sums=('8f6a9e7719d22004aee153db29ffd9ca41c7a6cd87fc791591994eecc2e625a1')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}

  ./configure --prefix=/usr --localstatedir=/var/games
  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}

  make DESTDIR=${pkgdir} install

  install -d ${pkgdir}/usr/share/pixmaps
  install -m644 icons/ltris{16,32,48}.xpm ${pkgdir}/usr/share/pixmaps
#FS#37951 fix  
  chmod 775 ${pkgdir}/var/games  
}
