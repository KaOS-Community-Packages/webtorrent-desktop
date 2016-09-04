pkgname=webtorrent-desktop
pkgver=0.14.0
pkgrel=1
pkgdesc="A streaming torrent client"
arch=('x86_64')
url="https://webtorrent.io/desktop"
license=('MIT')
depends=('gtk2' 'gconf' 'alsa-lib' 'libnotify' 'libxtst' 'nss')
source=("https://github.com/feross/$pkgname/releases/download/v${pkgver}/${pkgname}_${pkgver}-1_amd64.deb" "webtorrent-desktop.desktop" "webtorrent-desktop.png")
sha256sums=('fdf5a7c90b71e0f6a609900828745b39401be5c71aab526a8fbe14f44e98ec42'
            'ce832f86df17e21162eaf4ee43412502430fd566a326334f3fffd1d33fa28a78'
            'f7dec58d9e5e3a025377a9f789d6fc4f74c7c801fd3e0692e3b6c33f46f016f8')


package() {
    bsdtar -xf data.tar.gz -C ${pkgdir}
    chmod +x ${pkgdir}/opt/${pkgname}/WebTorrent
    install -dm755 $pkgdir/usr/bin
    ln -sf /opt/${pkgname}/WebTorrent ${pkgdir}/usr/bin/$pkgname
    install -Dm644 $srcdir/$pkgname.png $pkgdir/usr/share/pixmaps/$pkgname.png
    install -Dm644 $srcdir/$pkgname.desktop $pkgdir/usr/share/applications/$pkgname.desktop
}
