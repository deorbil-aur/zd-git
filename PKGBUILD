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

prepare() {
  cd "$srcdir/zd"
  cargo fetch --locked
}

build() {
  cd "$srcdir/zd"
  cargo build --release --frozen
}

package() {
  cd "$srcdir/zd"
  install -Dm755 "target/release/zd" "$pkgdir/usr/bin/zd"
  install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/zd/LICENSE"
  install -Dm644 "README.md" "$pkgdir/usr/share/doc/zd/README.md"
}
