# See AUR interface for current maintainer.

pkgname=ee
pkgver=1.5.2
pkgrel=2
_realname='easyedit'
pkgdesc='EasyEdit, a classic curses text editor. Born in HP-UX, used in FreeBSD.'
arch=('i686' 'x86_64')
url='http://www.users.qwest.net/~hmahon/'
license=('BSD')
depends=(ncurses)
makedepends=()
backup=()
source=("http://web.archive.org/web/20120716042037/http://mahon.cwx.net/sources/$pkgname-$pkgver.src.tgz"
	'BSD-2_clause')
sha256sums=('e08d7511a48b43ee354042fe3fe7d9cb3431238caedcf4ac729c61a447003918'
            '5b2531f7c9363e2bc2212cc8e20f321793319bf564353b20a189b852a0e562cb')

build() {
  cd "$srcdir/$_realname-$pkgver"

  ./create.make
  make -f make.local curses || return 1
}

package() {
  cd "$srcdir/$_realname-$pkgver"

  install -dm755 $pkgdir/usr/bin
  install -dm755 $pkgdir/usr/share/man/man1
  install -dm755 $pkgdir/usr/share/licenses/$pkgname

  install -sm755 ee $pkgdir/usr/bin
  install -m755  ee.1 $pkgdir/usr/share/man/man1
  install -m644 "$startdir/BSD-2_clause" $pkgdir/usr/share/licenses/$pkgname/LICENSE
}
