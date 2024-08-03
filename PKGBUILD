pkgname=bluez-qt
pkgver=6.4.0
pkgrel=1
pkgdesc='Qt wrapper for Bluez 5 DBus API'
arch=(x86_64)
url='https://github.com/LingmoOS/bluez-qt'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(bluez
         gcc-libs
         glibc
         qt6-base)
makedepends=(doxygen
             extra-cmake-modules
             qt6-declarative
             qt6-doc
             qt6-tools)
optdepends=('qt6-declarative: QML bindings')
groups=(kf6)
source=(git+$url)
sha256sums=('SKIP')
validpgpkeys=(53E6B47B45CEA3E0D5B7457758D0EE648A48B3BB # David Faure <faure@kde.org>
              E0A3EB202F8E57528E13E72FD7574483BB57B18D # Jonathan Esk-Riddell <jr@jriddell.org>
              90A968ACA84537CC27B99EAF2C8DF587A6D4AAC1 # Nicolas Fella <nicolas.fella@kde.org>
              )

build() {
  cmake -B build -S $pkgname \
    -DBUILD_TESTING=OFF \
    -DBUILD_QCH=ON
  cmake --build build -j12
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

