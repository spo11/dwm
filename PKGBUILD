# $Id: PKGBUILD 54496 2011-08-19 09:22:43Z spupykin $
# Maintainer: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Dag Odenhall <dag.odenhall@gmail.com>
# Contributor: Grigorios Bouzakis <grbzks@gmail.com>

pkgname=dwm
pkgver=5.9
pkgrel=2
pkgdesc="A dynamic window manager for X"
url="http://dwm.suckless.org"
arch=('i686' 'x86_64')
license=('MIT')
options=(zipman)
depends=('libx11' 'libxinerama')
install=dwm.install
source=(http://dl.suckless.org/dwm/dwm-$pkgver.tar.gz
	config.h
	dwm.desktop)
md5sums=('2799f885c05817ca112d521bb247f797'
         'f0ba59bf77a53e3a2fc8596740ee5cb8'
         '939f403a71b6e85261d09fc3412269ee')

build() {
  cd $srcdir/$pkgname-$pkgver
  cp $srcdir/config.h config.h
  sed -i 's/CPPFLAGS =/CPPFLAGS +=/g' config.mk
  sed -i 's/^CFLAGS = -g/#CFLAGS += -g/g' config.mk
  sed -i 's/^#CFLAGS = -std/CFLAGS += -std/g' config.mk
  sed -i 's/^LDFLAGS = -g/#LDFLAGS += -g/g' config.mk
  sed -i 's/^#LDFLAGS = -s/LDFLAGS += -s/g' config.mk
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make PREFIX=/usr DESTDIR=$pkgdir install
  install -m644 -D LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
  install -m644 -D README $pkgdir/usr/share/doc/$pkgname/README
  install -m644 -D $srcdir/dwm.desktop $pkgdir/usr/share/xsessions/dwm.desktop
}
md5sums=('2799f885c05817ca112d521bb247f797'
         '2763583d819b56023788814603c1b108'
         '939f403a71b6e85261d09fc3412269ee')
md5sums=('2799f885c05817ca112d521bb247f797'
         '96ea6d46c37b0cc1e7cb38f0f8f0e7e2'
         '939f403a71b6e85261d09fc3412269ee')
md5sums=('2799f885c05817ca112d521bb247f797'
         'e7fdf0adb4ae40dfcb548c17a2ab8c75'
         '939f403a71b6e85261d09fc3412269ee')
md5sums=('2799f885c05817ca112d521bb247f797'
         '035d68e4ace5888fa0faa7740173a5c3'
         '939f403a71b6e85261d09fc3412269ee')
md5sums=('2799f885c05817ca112d521bb247f797'
         'c41045450d16c4dd29c157c5bb5bff55'
         '939f403a71b6e85261d09fc3412269ee')
md5sums=('2799f885c05817ca112d521bb247f797'
         '96ea6d46c37b0cc1e7cb38f0f8f0e7e2'
         '939f403a71b6e85261d09fc3412269ee')
