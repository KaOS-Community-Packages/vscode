pkgname=vscode
pkgver=1.76.1
pkgrel=1
pkgdesc='Microsoft Visual Studio Code is a code editor Open Source'
arch=('x86_64')
url="https://code.visualstudio.com/"
license=('MIT')
depends=('gtk3' 'alsa-lib' 'libnotify' 'nss' 'libxtst' 'libxss' 'cairo' 'fontconfig' 'gcc-libs'
         'libnotify' 'glibc')
optdepends=('libdbusmenu-glib: to enable global menu (install via kcp)')
source=(vscode_${pkgver}_x86_64.tar.gz::https://update.code.visualstudio.com/${pkgver}/linux-x64/stable
        "${pkgname}.desktop")
md5sums=('4f9f6c11a462795b3cf40613aeb4165f'
         '20439bbbd1cb5fa5c8d9cb24a05f3b08')

package() {
    install -dm755 ${pkgdir}/usr/share/applications \
                   ${pkgdir}/opt/vscode \
                   ${pkgdir}/usr/share/icons \
                   ${pkgdir}/usr/share/licenses/${pkgname}

    cp -r ${srcdir}/VSCode-linux-x64/* ${pkgdir}/opt/vscode
    install -Dm644 ${pkgdir}/opt/vscode/resources/app/{LICENSE*,licenses/LICENSE*} ${pkgdir}/usr/share/licenses/${pkgname}/
    install -Dm644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
    install -m644 "${srcdir}/VSCode-linux-x64/resources/app/resources/linux/code.png" "${pkgdir}/usr/share/icons/code.png"
    install -dm755 ${pkgdir}/usr/bin
    ln -s /opt/vscode/bin/code ${pkgdir}/usr/bin/${pkgname}
    ln -s /opt/vscode/bin/code ${pkgdir}/usr/bin/code

    rm -rf ${pkgdir}/opt/vscode/resources/app/{LICENSE*,licenses}
}

