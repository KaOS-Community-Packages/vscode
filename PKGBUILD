pkgname=vscode
pkgver=1.10.2
pkgrel=1
_commit=8076a19fdcab7e1fc1707952d652f0bb6c6db331
_build=1488981323
pkgdesc='Microsoft Visual Studio Code is a code editor Open Source'
arch=('x86_64')
url="https://code.visualstudio.com/"
license=('MIT')
depends=('gtk2' 'alsa-lib' 'libnotify' 'nss' 'nodejs' 'gconf' 'libxtst')
source=("https://az764295.vo.msecnd.net/stable/${_commit}/code-stable-code_${pkgver}-${_build}_amd64.tar.gz"
        "${pkgname}.desktop"
        "code.svg")
md5sums=('299017b62461902f31c735177f7c7c71'
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
