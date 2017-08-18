pkgname=vscode
pkgver=1.15.1
pkgrel=1
_commit=41abd21afdf7424c89319ee7cb0445cc6f376959
# https://go.microsoft.com/fwlink/?LinkID=620884
_build=1502903936
pkgdesc='Microsoft Visual Studio Code is a code editor Open Source'
arch=('x86_64')
url="https://code.visualstudio.com/"
license=('MIT')
depends=('gtk2' 'alsa-lib' 'libnotify' 'nss' 'gconf' 'libxtst')
source=("https://az764295.vo.msecnd.net/stable/${_commit}/code-stable-code_${pkgver}-${_build}_amd64.tar.gz"
        "${pkgname}.desktop"
        "code.svg")
md5sums=('3332fc68a55e4e641dedea1bb15c7420'
         '20439bbbd1cb5fa5c8d9cb24a05f3b08'
         'ef58bc6b221e3e2dbf7f38376a381260')

package() {
    install -dm755 ${pkgdir}/usr/share/applications \
                   ${pkgdir}/opt/vscode \
                   ${pkgdir}/usr/share/icons/hicolor/scalable/apps \
                   ${pkgdir}/usr/share/licenses/${pkgname}

    cp -r ${srcdir}/VSCode-linux-x64/* ${pkgdir}/opt/vscode
    install -Dm644 ${pkgdir}/opt/vscode/resources/app/{LICENSE*,licenses/LICENSE*} \
            ${pkgdir}/usr/share/licenses/${pkgname}/
    install -Dm644 ${srcdir}/${pkgname}.desktop \
            ${pkgdir}/usr/share/applications/${pkgname}.desktop
    install -Dm644 ${srcdir}/code.svg \
            ${pkgdir}/usr/share/icons/hicolor/scalable/apps/code.svg
    install -dm755 ${pkgdir}/usr/bin
    ln -s /opt/vscode/bin/code ${pkgdir}/usr/bin/${pkgname}

    rm -rf ${pkgdir}/opt/vscode/resources/app/{LICENSE*,licenses,resources}
}
