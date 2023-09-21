# Maintainer: David K david.dk949@gmail.com
_pkgname=searocket
pkgname="${_pkgname}-949sd"
pkgver="unknown"
pkgrel=0
pkgdesc="slimmed down version of spaceship."
arch=('x86_64')
url="https://github.com/dk949/$_pkgname"
license=('MIT')
depends=('zsh')
makedepends=('ldc')
optdepends=('fc-list: to detect if Nerd fonts are available')
provides=(
    'searocket'
    'searocket.zsh'
)
source=("$pkgname::git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    git -C "$pkgname" describe | sed 's/-/_/g'
}

build() {
    cd "$pkgname"
    make -j
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
