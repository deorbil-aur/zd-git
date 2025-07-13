pkgname=zd-git
pkgver=0.2.3.r5.ga6ceb0d
pkgrel=1
pkgdesc="Extendable fuzzy directory selector"
arch=("x86_64")
url="https://github.com/deorbil/zd"
license=("MIT")
depends=("fzf")
makedepends=("cargo" "git")
provides=("zd")
conflicts=("zd")
options=("!lto")
source=("git+https://github.com/deorbil/zd.git")
sha256sums=("SKIP")

pkgver() {
  cd "$srcdir/zd"
  git describe --long | sed "s/^v//;s/\([^-]*-g\)/r\1/;s/-/./g"
}

build() {
  cd "$srcdir/zd"
  cargo build --release --locked
}

package() {
  cd "$srcdir/zd"
  install -Dm755 "target/release/zd" "$pkgdir/usr/bin/zd"
}
