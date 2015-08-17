# Maintainer: Clément Guérin <geecko.dev@free.fr>
# Contributor: Daniel Kirchner <daniel@ekpyron.rog>
# Contributor: Gustavo Alvarez <sl1pkn07@gmail.com>
# Contributor: Chase Geigle <sky@skystrife.com>

pkgname=sdl2-wayland-git
pkgver=20130728
pkgrel=1
pkgdesc="A library for portable low-level access to a video framebuffer, audio output, mouse, and keyboard (Version 2.0), with Wayland support."
arch=('i686' 'x86_64')
url="http://www.libsdl.org"
license=('ZLIB')
makedepends=('git' 'cmake')
depends=('sh' 'wayland')
provides=('sdl2')
conflicts=('sdl2' 'sdl2-hg')
source=('sdl2::git://github.com/soreau/SDL.git#branch=wayland-rebased-13-07-27')
md5sums=('SKIP')

build() {
  mkdir "${srcdir}/sdl2/build"
  cd "${srcdir}/sdl2/build"
  cmake .. -DCMAKE_INSTALL_PREFIX=/usr -DSDL_STATIC=OFF
  make
}

package() {
  cd "${srcdir}/sdl2/build"
  make DESTDIR="${pkgdir}/" install
  install -Dm644 ../COPYING.txt "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  install -Dm644 ../sdl2.m4 "${pkgdir}/usr/share/aclocal/sdl2.m4"
}
