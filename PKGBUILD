# Maintainer: icepie, icepie.dev@gmail.com

_pkgname=macast
_gitname=Macast
pkgname=${_pkgname}-git
pkgver=r143.d1aa55b
pkgrel=2
pkgdesc="DLNA Media Renderer"
arch=('any')
url="https://github.com/xfangfang/Macast"
license=('GPL3')
conflicts=('macast')
makedepends=('python-setuptools')
depends=(
	'python'
	'python-pillow'
	'python-pystray'
	'python-lxml'
	'python-pyperclip'
	'python-cherrypy'
	'mpv'
)
source=(
	"git+${url}.git#branch=dev"
	"${_pkgname}.desktop"
)
sha256sums=(
	'SKIP'
	'e55f7308c2620d0151d98f8f0e8bdd6fb5e80aa6f1464d5820a167e4b8c2ff14'
)

build() {
	cd "${_gitname}"
	python setup.py build
}

package() {
	cd "${_gitname}"
	install -d "${pkgdir}/usr/share/icons"
	cp "${_pkgname}/assets/icon.png" "${pkgdir}/usr/share/icons/Macast.png"
	install -d "${pkgdir}/usr/share/applications"
	# Installa desktop file
	mkdir -p "${pkgdir}/usr/share/applications"
	install -Dm644 "${srcdir}/${_pkgname}.desktop" "${pkgdir}/usr/share/applications/${_pkgname}.desktop"
	python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
