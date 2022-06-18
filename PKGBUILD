# Maintainer: Jeffrey Thompson <coldie@coldie.net>

pkgname=('otf-apple-sf-pro')
pkgver=0
pkgrel=1
pkgdesc="Apple designed sans-serif typeface that is the system font for watchOS"
url=https://developer.apple.com/fonts/
arch=('any')
license=('custom')
makedepends=('p7zip')
sha256sums=('SKIP')

source=("$pkgname-$pkgver.dmg::https://devimages-cdn.apple.com/design/resources/download/SF-Pro.dmg")
noextract=("$pkgname-$pkgver.dmg")

prepare() {
	mkdir -p "$pkgname-$pkgver"
	7z e -y -so "$pkgname-$pkgver.dmg" '-i!*/*.pkg' > $pkgname.pkg
	bsdtar -xOf $pkgname.pkg 'Resources/English.lproj/License.rtf' | xz > "$pkgname-$pkgver/LICENSE.rtf.xz"
	bsdtar -xOf $pkgname.pkg 'SFProFonts.pkg/Payload' > $pkgname.cpio
	bsdtar -C . -s ',.*/,,g' -xzf $pkgname.cpio \*.otf

	mv *.otf $pkgname-$pkgver
		
	mkdir -p "$pkgname-$pkgver"
	7z e -y -r "-o$pkgname-$pkgver" '-i!*.otf' "$pkgname.cpio"

	rm -f "$pkgname.pkg"
	rm -f "$pkgname.cpio"
}

package() {
	install -Dm644 $pkgname-$pkgver/LICENSE.rtf.xz "$pkgdir/usr/share/licenses/$pkgname/LICENSE.rtf.xz"
	install -d "$pkgdir/usr/share/fonts/OTF"
	install -m644 $pkgname-$pkgver/*.otf "$pkgdir/usr/share/fonts/OTF"
}
