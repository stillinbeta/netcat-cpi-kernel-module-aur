pkgname="netcat-cpi-kernel-module-git"
pkgver=r34.02a2bb8
pkgrel=1
pkgdesc="Cycles Per Instruction: A kernel-module album by netcat"
arch=('x86_64') # Haven't tested other platforms, may work
url="http://www.netcat.co/"
license=('custom')
makedepends=('git' 'linux-headers')
optdepends=('vorbis-tools: Play the stream')

install="hint.install"

source=("$pkgname::git+https://github.com/usrbinnc/netcat-cpi-kernel-module")
md5sums=("SKIP")

pkgver() {
    cd "$pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd $pkgname
    make
}

package() {
    install -D -m744 $pkgname/README.md $pkgdir/usr/share/docs/$pkgname/README.md
    install -D -m744 $pkgname/netcat.ko $pkgdir/usr/lib/$pkgname/netcat.ko
}
