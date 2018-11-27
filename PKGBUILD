# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname=linpac
pkgver=0.25
pkgrel=1
epoch=
pkgdesc="Amateur Radio AX.25 chat and PBBS program using Linux's AX.25 stack"
arch=(x86_64 x86)
url="https://sourceforge.net/projects/linpac/"
license=('GPL')
groups=()
depends=(bash perl ncurses libax25 ax25-apps)
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("http://downloads.sourceforge.net/project/linpac/LinPac/${pkgver}/${pkgname}-${pkgver}.tar.gz"
	"var-lock-fix.patch")
noextract=()
sha256sums=("00296f6f1cd61c745dc26e08985b62ddfdc5abaa7e191ad7a55cb66366986ea0"
	"56bcbe5d08f420667ccb70e925363124cf0018449617751848d1fc4e21f973fa")
validpgpkeys=()

prepare() {
	cd "$pkgname-$pkgver"
	patch -p1 -i "$srcdir/var-lock-fix.patch"
}

build() {
	cd "$pkgname-$pkgver"
	./configure --prefix=/usr --libexecdir=/usr/lib
	make
}

package() {
	cd "$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
}
