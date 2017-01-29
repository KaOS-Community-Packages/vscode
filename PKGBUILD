pkgname=vscode
pkgver=1.8.1
pkgrel=1
_commit=ee428b0eead68bf0fb99ab5fdc4439be227b6281
_build=1482158209
pkgdesc='Microsoft Visual Studio Code is a code editor Open Source'
arch=('x86_64')
url="https://code.visualstudio.com/"
license=('MIT')
depends=('gtk2' 'alsa-lib' 'libnotify' 'nss' 'nodejs' 'gconf' 'libxtst')
source=("https://az764295.vo.msecnd.net/stable/${_commit}/code-stable-code_${pkgver}-${_build}_amd64.tar.gz"
        "${pkgname}.desktop")
md5sums=('87ba1a58c33100e0184e1deb7c599c11'
         '5adf4fcf16bbb2fe842378106eddd87f')

package() {
    install -dm755 ${pkgdir}/usr/share/applications \
                   ${pkgdir}/opt/VSCode \
                   ${pkgdir}/usr/share/icons/hicolor/512x512/apps \
                   ${pkgdir}/usr/share/licenses/${pkgname}

    cp -r ${srcdir}/VSCode-linux-x64/* ${pkgdir}/opt/VSCode
    install -Dm644 ${pkgdir}/opt/VSCode/resources/app/{LICENSE*,licenses/LICENSE*} ${pkgdir}/usr/share/licenses/${pkgname}/
    install -Dm644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
    install -Dm644 ${pkgdir}/opt/VSCode/resources/app/resources/linux/code.png ${pkgdir}/usr/share/icons/hicolor/512x512/apps/
    install -dm755 ${pkgdir}/usr/bin
    ln -s /opt/VSCode/bin/code ${pkgdir}/usr/bin/${pkgname}

    rm -rf ${pkgdir}/opt/VSCode/resources/app/{LICENSE*,licenses,resources}
}