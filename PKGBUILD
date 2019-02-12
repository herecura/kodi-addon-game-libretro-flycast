# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-game-libretro-reicast
pkgver=0.1.0.10
_codename=Leia
pkgrel=1
pkgdesc="Libretro wrapper for Kodi's Game API"
arch=('x86_64')
url='https://github.com/kodi-game/game.libretro.reicast'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-game')
depends=('kodi-addon-game-libretro' 'libretro-reicast')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/kodi-game/game.libretro.reicast/archive/$pkgver-$_codename.tar.gz")
sha512sums=('341e1dc70d64689af7cc93fda15304aaf62790b310bf7a9116e893092f98c4ec0103075cdc5d6b460e719f2f5d783990e06bc2dce13d4a99f3cf19411b96947d')

build() {
    cd "game.libretro.reicast-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "game.libretro.reicast-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

