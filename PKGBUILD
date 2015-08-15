# Maintainer:
_hkgname=cabal-dev
pkgname=cabal-dev
pkgver=0.9.2
pkgrel=2
pkgdesc="Manage sandboxed Haskell build environments"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc'
             'haskell-cabal'
             'haskell-http'
             'haskell-mtl'
             'haskell-bytestring'
             'haskell-containers'
             'haskell-directory'
             'haskell-network'
             'haskell-tar'
             'haskell-transformers'
             'haskell-zlib'
             'haskell-setenv')
depends=('gmp'
         'zlib'
         'cabal-install')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
md5sums=('bc9376151b184a6630eaa0b2ad05f927')
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
