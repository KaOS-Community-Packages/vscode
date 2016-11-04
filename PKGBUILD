pkgname=vscode
pkgver=1.7.1
pkgrel=1
_commit=02611b40b24c9df2726ad8b33f5ef5f67ac30b44
_build=1478180561
pkgdesc='Microsoft Visual Studio Code is a code editor Open Source'
arch=('x86_64')
url='https://code.visualstudio.com/'
license=('MIT')
depends=('gtk2' 'alsa-lib' 'libnotify' 'nss' 'nodejs' 'gconf' 'libxtst')
source=("https://az764295.vo.msecnd.net/stable/${_commit}/code-stable-code_${pkgver}-${_build}_amd64.tar.gz" )
md5sums=('2b7261f2bd51147e9413990f6fc795e2')
package() {
    install -dm755 ${pkgdir}/usr/share/applications
    echo -en '[Desktop Entry]\nName=Visual Studio Code\nExec=/opt/VSCode/bin/code\nIcon=/opt/VSCode/resources/app/resources/linux/code.png\nType=Application\nCategories=Development;' > ${pkgdir}/usr/share/applications/${pkgname}.desktop
    install -dm755 ${pkgdir}/opt/VSCode
    cp -r ${srcdir}/VSCode-linux-x64/* ${pkgdir}/opt/VSCode
    install -dm755 ${pkgdir}/usr/bin
    ln -s /opt/VSCode/bin/code ${pkgdir}/usr/bin/${pkgname}
}
