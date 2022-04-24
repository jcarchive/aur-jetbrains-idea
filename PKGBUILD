# Maintainer: Jose C.

pkgname=jetbrains-idea
pkgver=2022.1
pkgrel=1
pkgdesc="Integrated development environment written in Java for developing computer software"
arch=('x86_64')
options=('!strip')
url="https://www.jetbrains.com/idea/"
license=('Commercial')
provides=('idea')
conflicts=('idea')

_filename="ideaIU-$pkgver.tar.gz"
_filextract="idea-IU-221.5080.210"

source=("https://download.jetbrains.com/idea/ideaIU-$pkgver.tar.gz"
	"${pkgname}.desktop")

sha256sums=( 
  '6ec9623d995e519968edfde73be7b3178bf0e345c86a08cfbfcaef341e7f346e'
  'a622a9e0f4719317d06e8b02b2d91fb0ad0b4db11ba919deed0571cf1099bb2e'
)

package() {
	#Create directories with permission rwxr-xr-x
	install -m755 -d "${pkgdir}/usr/share" "${pkgdir}/usr/bin" "${pkgdir}/usr/share/applications"

	#Copy files to pkg destination
	cp -r "${srcdir}/${_filextract}" "${pkgdir}/usr/share/${pkgname}"
  chown -R root:root "${pkgdir}/usr/share/${pkgname}"

	ln -s "/usr/share/${pkgname}/bin/idea.sh" "${pkgdir}/usr/bin/idea"
  install -m644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications"
}
