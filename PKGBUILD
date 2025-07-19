# Maintainer: Trevin Jones <trevindjones at gmail dot com>
pkgname=swayenv
pkgver=1.0
pkgrel=1
pkgdesc="Easily define environment variables for Sway on session startup"
arch=(any)
url="https://github.com/trevin-j/swayenv"
license=('MIT')
depends=('sway' 'bash')
backup=("etc/sway/environment")
source=("swayenv" "swayenv.desktop" "environment")
sha256sums=('SKIP' # Replace with actual checksums after packaging
           'SKIP'
           'SKIP')

package() {
    # 1. Install wrapper script
    install -Dm755 "$srcdir/swayenv" "$pkgdir/usr/bin/swayenv"

    # 2. Install system environment file
    install -Dm644 "$srcdir/environment" "$pkgdir/etc/sway/environment"

    # 3. Install desktop entry
    install -Dm644 "$srcdir/swayenv.desktop" "$pkgdir/usr/share/wayland-sessions/swayenv.desktop"
}
