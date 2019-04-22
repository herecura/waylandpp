# Maintainer: Nils Christopher Brause <nilschrbrause@googlemail.com>
pkgname=waylandpp
pkgver=0.2.3
pkgrel=1
pkgdesc='Wayland C++ bindings'
arch=('x86_64')
url='https://github.com/NilsBrause/waylandpp'
license=('MIT' 'GPL3')
depends=(wayland)
conflicts=(waylandpp-git)
makedepends=(cmake egl-wayland)
source=("https://github.com/NilsBrause/waylandpp/archive/$pkgver.zip")
sha512sums=('ea801c4cc3fbfbeacbed1dee2545556bbdbcf750edb79147292306a47c4e29f57cf0a9f27a4b36a66caef04385bfa9b8c89c311ca749d7869d9ee49de5fd7751')

build()
{
    cd $pkgname-$pkgver
    [[ -d build ]] && rm -rf build
    mkdir build
    cd build
    # lib64 is a symlink to lib on archlinux.
    cmake -DCMAKE_INSTALL_PREFIX="/usr" -DCMAKE_INSTALL_LIBDIR="lib" .. 
    make
}

package()
{
    cd $pkgname-$pkgver/build
    DESTDIR="$pkgdir" make install
}
