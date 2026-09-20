# Maintainer: Z.ai community package maintainers
pkgname=zcode
pkgver=3.14.1
pkgrel=1
pkgdesc='ZCode Desktop App'
arch=('x86_64')
url='https://zcode.z.ai/en'
license=('unknown')
depends=('gtk3' 'libnotify' 'nss' 'libxss' 'libxtst' 'xdg-utils' 'at-spi2-core' 'util-linux-libs' 'libsecret')
optdepends=('libappindicator-gtk3: system tray indicator support')
options=('!strip')
source=("ZCode-${pkgver}-linux-x64.deb::https://cdn-zcode.z.ai/zcode/electron/releases/${pkgver}/linux-x64/ZCode-${pkgver}-linux-x64.deb")
sha256sums=('2ba6d9d130fdf22af500f555a2c289fa5300712dd97052231251f8782ada3fdf')

package() {
    local deb="${srcdir}/ZCode-${pkgver}-linux-x64.deb"
    local debdir="${srcdir}/debian"

    install -d "${debdir}"
    bsdtar -xf "${deb}" -C "${debdir}"
    bsdtar -xpf "${debdir}/data.tar.xz" -C "${pkgdir}"

    install -d "${pkgdir}/usr/bin"
    ln -s /opt/ZCode/zcode "${pkgdir}/usr/bin/zcode"
}
