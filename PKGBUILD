pkgname=vscode
pkgver=1.1.1
pkgrel=1
_commit=def9e32467ad6e4f48787d38caf190acbfee5880
pkgdesc='Microsoft Visual Studio Code is a code editor Open Source'
arch=('x86_64')
url='https://code.visualstudio.com/'
license=('MIT')
depends=('gtk2' 'alsa-lib' 'libnotify' 'nss' 'nodejs' 'gconf' 'libxtst')
source=("https://az764295.vo.msecnd.net/stable/${_commit}/VSCode-linux-x64-stable.zip" )
md5sums=('4fcac208668193c80d1eb167f6ccc6be')

package() {
    install -dm755 ${pkgdir}/usr/share/applications
    echo -en '[Desktop Entry]\nName=Visual Studio Code\nExec=/opt/VSCode/code\nIcon=/opt/VSCode/resources/app/resources/linux/code.png\nType=Application\nCategories=Development;' > ${pkgdir}/usr/share/applications/${pkgname}.desktop
    install -dm755 ${pkgdir}/opt/VSCode
    cp -r ${srcdir}/VSCode-linux-x64/* ${pkgdir}/opt/VSCode
    install -dm755 ${pkgdir}/usr/bin
    ln -s /opt/VSCode/code ${pkgdir}/usr/bin/${pkgname}
}

