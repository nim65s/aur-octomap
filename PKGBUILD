# Maintainer: acxz <akashpatel2008 at yahoo dot com>
# Contributor: Andrew Sun <adsun701 at gmail dot com>
# Contributor: Benjamin Chrétien <chretien dot b+arch at gmail dot com>
# Contributor: Soo-Hyun Yoo <yoos117 at gmail dot com>
# Contributor: Guilhem Saurel <guilhem.saurel at laas dot fr>

pkgname=octomap
pkgver=1.10.0
pkgrel=1
pkgdesc="Efficient probabilistic 3D mapping framework based on octrees"
arch=('i686' 'x86_64')
url="https://github.com/$pkgname/$pkgname"
license=('BSD-3-Clause')
depends=('gcc-libs' 'qt5-base' 'glu' 'libglvnd' 'glibc')
makedepends=('cmake')
provides=('octomap')
conflicts=('octomap-git')
options=('staticlibs')
source=("${pkgname}-${pkgver}.tar.gz"::"$url/archive/v${pkgver}.tar.gz")
sha256sums=('8da2576ec6a0993e8900db7f91083be8682d8397a7be0752c85d1b7dd1b8e992')

build() {
    cmake -B "build-$pkgver" -S "$pkgbase-$pkgver" \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -Wno-dev
    cmake --build "build-$pkgver"
}

package() {
    DESTDIR="$pkgdir/" cmake --build "build-$pkgver" -t install
    install -Dm644 "$pkgbase-$pkgver/$pkgbase/LICENSE.txt" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
