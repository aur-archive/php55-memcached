# $Id$
# Maintainer: Evangelos Foutras <evangelos@foutrelis.com>

pkgname=php55-memcached
pkgver=2.1.0
pkgrel=2
pkgdesc="PHP extension for interfacing with memcached via libmemcached library"
arch=('i686' 'x86_64')
url="http://pecl.php.net/package/memcached"
license=('PHP')
depends=('php55' 'libmemcached')
backup=('etc/php/conf.d/memcached.ini')
source=(http://pecl.php.net/get/memcached-$pkgver.tgz)
sha256sums=('bc4940015be74f47908d410d7b55e10a3d5bf65674036d944c73558227fcc4af')

build() {
  cd "$srcdir/memcached-$pkgver"

  phpize
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/memcached-$pkgver"

  make INSTALL_ROOT="$pkgdir" install
  echo ';extension=memcached.so' >memcached.ini
  install -Dm644 memcached.ini "$pkgdir/etc/php/conf.d/memcached.ini"
}

# vim:set ts=2 sw=2 et:
