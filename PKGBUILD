pkgname=htmlcxx
pkgver=0.85
pkgrel=1
pkgdesc="A simple non-validating CSS1 and HTML parser for C++."
arch=('x86_64')
url="http://htmlcxx.sourceforge.net/"
license=('LGPL')
source=("http://heanet.dl.sourceforge.net/project/${pkgname}/${pkgname}/${pkgver}/${pkgname}-${pkgver}.tar.gz"
        "missing-header.patch")
sha256sums=('ab02a0c4addc82f82d564f7d163fe0cc726179d9045381c288f5b8295996bae5'
            '2df7ea556410979f4ede3cb70d2067ba83eaadd437e3f68d67d0834cc8e4d33c')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	
	patch -p1 -i "${srcdir}/missing-header.patch"

	LDFLAGS="$LDFLAGS -Wl,--no-as-needed"
	./configure --prefix=/usr
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="${pkgdir}" install
}
