# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-game-libretro-reicast
pkgver=0.1.0.9
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
sha512sums=('9a97b5218621124795662fe3409445a8ab312b4d692ec8bdafc0c75cebf0fbb7511528321304849a998df008ef50d534435dcc53435c268b64a65f3e8f931c4b')

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

