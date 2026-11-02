# Maintainer: Z.ai community package maintainers
pkgname=zcode
pkgver=3.17.2
pkgrel=1
pkgdesc='ZCode Desktop App'
arch=('x86_64')
url='https://zcode.z.ai/en'
license=('unknown')
depends=('gtk3' 'libnotify' 'nss' 'libxss' 'libxtst' 'xdg-utils' 'at-spi2-core' 'util-linux-libs' 'libsecret')
optdepends=('libappindicator-gtk3: system tray indicator support')
options=('!strip')
source=("ZCode-${pkgver}-linux-x64.deb::https://cdn-zcode.z.ai/zcode/electron/releases/${pkgver}/linux-x64/ZCode-${pkgver}-linux-x64.deb")
sha256sums=('86ec7b2a795c46ae56e7313504300a337c33c68267c28f96a03726a4f5aff575')

package() {
    local deb="${srcdir}/ZCode-${pkgver}-linux-x64.deb"
    local debdir="${srcdir}/debian"

    install -d "${debdir}"
    bsdtar -xf "${deb}" -C "${debdir}"
    bsdtar -xpf "${debdir}/data.tar.xz" -C "${pkgdir}"

    install -d "${pkgdir}/usr/bin"
    ln -s /opt/ZCode/zcode "${pkgdir}/usr/bin/zcode"
}
