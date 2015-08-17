# Maintainer: Jonas Heinrich <onny@project-insanity.org>
# Contributor: Jonas Heinrich <onny@project-insanity.org>

pkgname=python2-wader
_pkgname=wader
pkgver=0.5.12
pkgrel=4
pkgdesc="Wader - Modem Manager compatible core"
arch=('any')
url="https://github.com/andrewbird/wader"
license=('GPL2')
depends=('python2' 'python2-gudev' 'epsilon')
source=("https://github.com/andrewbird/$_pkgname/archive/${pkgver}.tar.gz")
sha512sums=('10ad649e057695c26af937581fe5581a7dd932e7e345ac9df2d490f6bb135fb856496585b0c1f0f4ba5de6fa3955c487ea29d08cabf5a2ef1df86d90b09284e7')

build() {
  cd ${srcdir}/${_pkgname}-${pkgver}
  python2 setup.py build
}
package() {
  cd ${srcdir}/${_pkgname}-${pkgver}
  python2 setup.py install --root=$pkgdir
  sed -i '1s/python/python2/' ${pkgdir}/usr/bin/wader-core-ctl
  sed -i '39s/Ubuntu/arch/' ${pkgdir}/usr/share/wader-core/plugins/ubuntu.py
}
