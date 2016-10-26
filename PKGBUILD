pkgname=dwm-git-noisu
_pkgname=dwm
pkgver=6.1.8.g590b059
pkgrel=1
pkgdesc="A dynamic window manager for X"
url="http://dwm.suckless.org"
arch=('i686' 'x86_64')
license=('MIT')
options=(zipman)
depends=('libx11' 'libxinerama' 'libxft')
makedepends=('git')
provides=('dwm')
conflicts=('dwm')
source=("$_pkgname::git+http://git.suckless.org/dwm")
md5sums=('SKIP')

pkgver(){
  cd $_pkgname
  git describe --tags |sed 's/-/./g'
}

prepare() {
  cd $_pkgname

  # merge user branch only if it exists
  if [[ $(git branch | grep -Po "user") == "user" ]]; then
    git merge user
  fi
}

build() {
  cd $_pkgname
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd $_pkgname
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -m644 -D README "$pkgdir/usr/share/doc/$pkgname/README"

  if [[ $(git branch | grep -Po "user") == "user" ]]; then
    git checkout user
  fi
}

# vim:ts=2:sw=2:et:
