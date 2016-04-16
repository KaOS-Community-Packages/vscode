pkgname=vscode
pkgver=1.0.0
pkgrel=1
_commit=fa6d0f03813dfb9df4589c30121e9fcffa8a8ec8
pkgdesc='Microsoft Visual Studio Code is a code editor Open Source'
arch=('x86_64')
url='https://code.visualstudio.com/'
license=('MIT')
depends=('gtk2' 'gconf')
install=${pkgname}.install
source=("https://az764295.vo.msecnd.net/stable/${_commit}/VSCode-linux-x64-stable.zip" )
md5sums=('fb506db2edc24291b7ea25e3bc93e974')

package() {
    install -dm755 ${pkgdir}/usr/share/applications
    echo -en '[Desktop Entry]\nName=Visual Studio Code\nExec=/opt/VSCode/code\nIcon=/opt/VSCode/resources/app/resources/linux/code.png\nType=Application\nCategories=Development;' > ${pkgdir}/usr/share/applications/${pkgname}.desktop
    install -dm755 ${pkgdir}/opt/VSCode
    cp -r ${srcdir}/VSCode-linux-x64/* ${pkgdir}/opt/VSCode
    install -dm755 ${pkgdir}/usr/bin
    ln -s /opt/VSCode/code ${pkgdir}/usr/bin/${pkgname}
}
