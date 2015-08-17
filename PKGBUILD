# $Id$
# Maintainer: Brett L Kleinschmidt <blk@blk.me>
# Contributor: Brett L Kleinschmidt <blk@blk.me>

pkgbase=python-maxminddb
pkgname=('python-maxminddb' 'python2-maxminddb')
pkgver=0.3.3
pkgrel=2
pkgdesc="Python module for reading MaxMind DB files"
arch=('i686' 'x86_64')
url="https://pypi.python.org/pypi/maxminddb"
license=('Apache')
makedepends=('python' 'python2')
optdepends=('libmaxminddb-git: C backend')
source=(https://pypi.python.org/packages/source/m/maxminddb/maxminddb-${pkgver}.tar.gz)
md5sums=('36e1ca4e46e3220aa6a2aee1b58d9d88')

prepare() {
  cp -a "maxminddb-$pkgver"{,-py2}
}

build() {
  cd "maxminddb-$pkgver"
  python setup.py build

  cd "../maxminddb-$pkgver-py2"
  python2 setup.py build
}

package_python-maxminddb() {
depends=('python')

  cd "maxminddb-$pkgver"
  python setup.py install --root="$pkgdir" -O1
}

package_python2-maxminddb() {
  depends=('python2' 'python2-ipaddr')

  cd "maxminddb-$pkgver-py2"
  python2 setup.py install --root="$pkgdir" -O1
}

# vim:set ts=2 sw=2 et:
