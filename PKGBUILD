#Autor programu: Iliya Kobzev aka TechnoMag (vendor7@yandex.ru)
# Opiekun: TechnoMag82 <mail at somewhere dot>
# url autora programu: https://github.com/TechnoMag82/UrlCollector.git
# PKGBUILD: nycko123 <nycko123 at google>
# Spolszczenie programu UrlCollector: Krzysztof Jaśkiewicz
pkgname=url-collector-qt5
_pkgname=UrlCollector
pkgver=2.0
pkgrel=1
pkgdesc="Program do tworzenia tekstowej bazy danych linków internetowych."
arch=('x86_64')
depends=('qt5-base')

license=('GPL')

# source=("${_pkgname}-${pkgver}.tar.gz::https://github.com/TechnoMag82/UrlCollector/archive/refs/tags/v${pkgver}.tar.gz")

source=("${_pkgname}-${pkgver}.tar.gz::UrlCollector-2.0.tar.gz")

sha512sums=('4a8083967145cb4f07929e561a5f0f282c52b761af4c60948e7daea29b2d009faa089de8db96fd68d3323367e829d325e88dbb9842afc9348090e9ea944e6561')

prepare(){
	cd "${srcdir}/${_pkgname}-${pkgver}"
	lrelease-qt5 main_pl.ts
	qmake-qt5 -makefile
}

build(){
	cd "${srcdir}/${_pkgname}-${pkgver}"
	make
}

package(){
	install -Dm755 "${srcdir}/${_pkgname}-${pkgver}/UrlCol" "${pkgdir}/usr/bin/urlcol"
	install -Dm644 "${srcdir}/${_pkgname}-${pkgver}/package/urlcollector/usr/share/applications/urlcollector.desktop" "${pkgdir}/usr/share/applications/urlcollector.desktop"
	install -Dm644 "${srcdir}/${_pkgname}-${pkgver}/package/urlcollector/usr/share/pixmaps/urlcollector.png" "${pkgdir}/usr/share/pixmaps/urlcollector.png"
}