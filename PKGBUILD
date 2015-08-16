# Contributor: Alessio Sergi <asergi at archlinux dot us>
# Maintainer: ava1ar <mail(at)ava1ar(dot)info>

pkgname=kdeplasma-applets-ihatethecashew
pkgver=0.4
pkgrel=2
pkgdesc="A plasmoid that remove the cashew"
arch=('i686' 'x86_64')
url="http://kde-look.org/content/show.php/I+HATE+the+Cashew?content=91009"
license=('GPL2')
depends=('kdelibs')
makedepends=('automoc4' 'cmake')
source=("http://www.kde-look.org/CONTENT/content-files/91009-iHateTheCashew-4.4.tbz"
        "ihtc-fix.patch")
sha1sums=('b91b5e4ab3bd1c8b0d0185c3e852edaf89f06667'
          '23b3681ca0a2b0d027f0beabecc0505afb4d49af')

prepare() {
  patch -Np0 -d iHateTheCashew -i "$srcdir"/ihtc-fix.patch
  mkdir "$srcdir"/build
}

build() {
  cd "$srcdir"/build
  cmake ../iHateTheCashew \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DQT_QMAKE_EXECUTABLE=qmake-qt4
  make
}

package() {
  cd "$srcdir"/build
  make DESTDIR="$pkgdir" install
}
