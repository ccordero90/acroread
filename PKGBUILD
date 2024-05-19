# Maintainer: Geballin - Guillaume Ballin <macniaque at free dot fr>
# Contributor: Tucker Boniface <tucker@boniface.tech>
# Contributor: Tom Kwok <contact@tomkwok.com>
# Contributor: Jose Valecillos <valecillosjg at gmail dot com>
# Contributor: Guido <qqqqqqqqq9 at web dot de>
# Contributor: Limao Luo <luolimao+AUR at gmail com>
# Contributor: Alexander Fehr <pizzapunk at gmail dot com>
# Olivier Esser: Add needed old versions of lib32-glib2 and lib32-harfbuzz <olivier dot esser at gmail dot com>

pkgname=acroread
pkgver=9.5.5
pkgrel=20
pkgdesc="Adobe Acrobat Reader is a PDF file viewer"
arch=('i686' 'x86_64')
url="http://www.adobe.com/products/reader/"
license=(custom)
optdepends=('acroread-fonts: CJK and extended font packs'
            'libcanberra: XDG sound support'
            'gtk-engine-murrine: fix ugly buttons and scrollbars'
            )
depends=('desktop-file-utils' lib32-{at-spi2-atk,libcanberra,cairo,libxinerama,libxi,libxrandr,libxcursor,libxcomposite,fribidi,libthai,mesa,glu})
optdepends=('acroread-fonts: CJK and extended font packs'
            'lib32-gtk-engine-murrine: fix ugly buttons and scrollbars')
options=(!strip)
install=$pkgname.install
source=($pkgname.desktop
        http://ardownload.adobe.com/pub/adobe/reader/unix/9.x/$pkgver/enu/AdbeRdr$pkgver-1_i486linux_enu.bin
	https://archive.archlinux.org/packages/l/lib32-glib2/lib32-glib2-2.58.3-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-harfbuzz/lib32-harfbuzz-2.3.1-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-pango/lib32-pango-1:1.43.0-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-librsvg/lib32-librsvg-2.44.12-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-gdk-pixbuf2/lib32-gdk-pixbuf2-2.38.1-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-libxml2/lib32-libxml2-2.10.1-1-x86_64.pkg.tar.zst
	https://archive.archlinux.org/packages/l/lib32-gtk2/lib32-gtk2-2.24.32-2-x86_64.pkg.tar.zst
	https://archive.archlinux.org/packages/l/lib32-libxt/lib32-libxt-1.2.0-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-libidn/lib32-libidn-1.36-1-x86_64.pkg.tar.zst
	https://archive.archlinux.org/packages/l/lib32-icu/lib32-icu-64.1-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-atk/lib32-atk-2.32.0-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-cairo/lib32-cairo-1.16.0-2-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-libffi/lib32-libffi-3.2.1-2-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-libx11/lib32-libx11-1.6.10-1-x86_64.pkg.tar.zst
	https://archive.archlinux.org/packages/l/lib32-freetype2/lib32-freetype2-2.10.0-1-x86_64.pkg.tar.xz
	https://archive.archlinux.org/packages/l/lib32-fontconfig/lib32-fontconfig-2:2.13.91+24+g75eadca-1-x86_64.pkg.tar.xz)
	
noextract=("${source[@]%%::*}")
sha512sums=('178ca8a3abf630195eaebd6a76a7e5ac19165708acd52b99acab2de3d0bdb57fdf81d666edae41a947fa5a3fc14442c86fa855860d5d3d0d3e1db0386c583b96'
            'f9c18ca0dc0687de353afeb90925439a557a14604e6361ff2b229ec29257ff051ea9eac6a90671b38a745473b5c87135377d035520f441ceaabf2510d690675b')
prepare() {
    # Extracting content from bin file
    tail -c+6889 AdbeRdr9.5.5-1_i486linux_enu.bin | xz -qqd | tar x
    mkdir oldlib
    tar -C oldlib -axf 'lib32-glib2-2.58.3-1-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-harfbuzz-2.3.1-1-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-pango-1:1.43.0-1-x86_64.pkg.tar.xz' --force-local
    tar -C oldlib -axf 'lib32-librsvg-2.44.12-1-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-gdk-pixbuf2-2.38.1-1-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-libxml2-2.10.1-1-x86_64.pkg.tar.zst'
    tar -C oldlib -axf 'lib32-gtk2-2.24.32-2-x86_64.pkg.tar.zst'
    tar -C oldlib -axf 'lib32-libxt-1.2.0-1-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-libidn-1.36-1-x86_64.pkg.tar.zst'
    tar -C oldlib -axf 'lib32-icu-64.1-1-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-atk-2.32.0-1-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-cairo-1.16.0-2-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-libffi-3.2.1-2-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-libx11-1.6.10-1-x86_64.pkg.tar.zst'
    tar -C oldlib -axf 'lib32-freetype2-2.10.0-1-x86_64.pkg.tar.xz'
    tar -C oldlib -axf 'lib32-fontconfig-2:2.13.91+24+g75eadca-1-x86_64.pkg.tar.xz' --force-local

    cd AdobeReader/
    bsdtar -xf COMMON.TAR
    bsdtar -xf ILINXR.TAR

    sed -i "s/_filedir/&_acroread/" Adobe/Reader9/Resource/Shell/acroread_tab
    # Bug on log created by Adobe Reader browser plugin https://bugs.launchpad.net/ubuntu/+source/acroread/+bug/986841
    sed -i 's#C:\\nppdf32Log\\debuglog\.txt#/dev/null\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00#g' \
Adobe/Reader9/Browser/intellinux/nppdf.so
}

package() {
    desktop-file-install $pkgname.desktop --dir "$pkgdir"/usr/share/applications/

    msg2 "Copying old libraries"
    install -d "$pkgdir/opt/Adobe/Reader9/Reader/intellinux/lib"
    cp -a oldlib/usr/lib32/* "$pkgdir/opt/Adobe/Reader9/Reader/intellinux/lib"

    cd AdobeReader/Adobe/Reader9/

    msg2 "Installing Main Files..."
    install -d "$pkgdir"/opt/Adobe/Reader9
    cp -a * "$pkgdir"/opt/Adobe/Reader9/

    msg2 "Installing Bin Files..."
    install -d "$pkgdir"/usr/bin/
    ln -s /opt/Adobe/Reader9/bin/acroread "$pkgdir"/usr/bin/
    install -Dm644 Resource/Shell/acroread.1.gz "$pkgdir"/usr/share/man/man1/acroread.1.gz
    install -Dm644 Resource/Shell/acroread_tab "$pkgdir"/etc/bash_completion.d/acroread

    msg2 "Installing Icon Resources..."
    install -Dm644 Resource/Icons/64x64/AdobeReader9.png "$pkgdir"/usr/share/pixmaps/$pkgname.png

    msg2 "Installing License..."
    install -Dm644 Reader/Legal/en_US/License.txt "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
