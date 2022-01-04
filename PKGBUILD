# Maintainer: Jose C.

pkgname=jetbrains-idea
pkgver=2021.3.1
pkgrel=1
pkgdesc="Integrated development environment written in Java for developing computer software"
arch=('x86_64')
options=('!strip')
url="https://www.jetbrains.com/idea/"
license=('Commercial')
provides=('idea')
conflicts=('idea')

_filename="JetBrains.Idea-${pkgver}.tar.gz"
_filextract="idea-IU-213.6461.79"

source=("https://download.jetbrains.com/idea/ideaIU-2021.3.1.tar.gz"
	"${pkgname}.desktop")

sha256sums=( 'a15b94ea5311b740d08171f0a2fc4d2a60333268082ffb1ae097b47525ce6387'
	'c30f65f567e5a085fc52e8128928f644a813ec0e436065c16e7b92938ff3a532')

package() {
	#Create directories with permission rwxr-xr-x
	install -m755 -d "${pkgdir}/usr/share" "${pkgdir}/usr/bin" "${pkgdir}/usr/share/applications"

	#Copy files to pkg destination
	cp -r "${srcdir}/${_filextract}" "${pkgdir}/usr/share/${pkgname}"
  chown -R root:root "${pkgdir}/usr/share/${pkgname}"

	ln -s "/usr/share/${pkgname}/bin/idea.sh" "${pkgdir}/usr/bin/idea"
  install -m644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications"
}
