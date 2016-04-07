pkgname=vscode
pkgver=0.10.11
pkgrel=1
_commit=f291f4ad600767626b24a4b15816b04bee9a3049
pkgdesc='Microsoft Visual Studio Code is a code editor Open Source'
arch=('x86_64')
url='https://code.visualstudio.com/'
license=('MIT')
depends=('gtk2' 'gconf')
install=${pkgname}.install
source=("https://az764295.vo.msecnd.net/stable/${_commit}/VSCode-linux-x64-stable.zip" )
md5sums=('f2ef5738542d1c800b577fd38020424b')

package() {
    install -dm755 ${pkgdir}/usr/share/applications
    echo -en '[Desktop Entry]\nName=Visual Studio Code\nExec=/opt/VSCode/code\nIcon=/opt/VSCode/resources/app/resources/linux/code.png\nType=Application\nCategories=Development;' > ${pkgdir}/usr/share/applications/${pkgname}.desktop
    install -dm755 ${pkgdir}/opt/VSCode
    cp -r ${srcdir}/VSCode-linux-x64/* ${pkgdir}/opt/VSCode
    install -dm755 ${pkgdir}/usr/bin
    ln -s /opt/VSCode/code ${pkgdir}/usr/bin/${pkgname}
}
