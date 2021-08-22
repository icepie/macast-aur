# Maintainer: icepie, icepie.dev@gmail.com

_pkgname=macast
__pkgname=Macast
pkgname=${_pkgname}-git
pkgver=r102.7447b2b
pkgrel=1
pkgdesc="A menu bar application using mpv as DLNA Media Renderer. You can push videos, pictures or musics from your mobile phone to your computer."
arch=('any')
url="https://github.com/xfangfang/Macast"
license=('GPL3')
conflicts=('macast')
depends=(
	'python'
	'python-setuptools'
	'python-pillow'
	'python-pystray'
	'python-lxml'
	'python-pyperclip'
	'python-cherrypy'
	'python-pip'
	'mpv'
	)
source=(git+"${url}.git")
sha256sums=('SKIP')

pkgver() {
	cd "$__pkgname"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "${srcdir}/${__pkgname}"
	#python setup.py build
}

package() {
	install -d  "$pkgdir"/opt/"${_pkgname}"
	cp -r  "${__pkgname}" "${pkgdir}/opt/"
 	install -d "${pkgdir}/usr/share/applications"
	 
}
