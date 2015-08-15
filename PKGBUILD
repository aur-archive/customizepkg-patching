# Author: Daniel Oertwig <Daniel.Oertwig+customizepkgpatching at gmail dot com>
pkgname=customizepkg-patching
pkgver=18.80b8860
pkgrel=1
pkgdesc="A tool to automate modification of PKGBUILDs using patch" 
url="https://github.com/DanielOertwig/customizepkg-patching" 
license="GPL" 
arch=('any')
depends=('bash' 'diffutils' 'patch')
optdepends=('vim: For using vimdiff')
provides=(customizepkg)
conflicts=(customizepkg)
source=('git://github.com/DanielOertwig/customizepkg-patching#branch=release') 
md5sums=('SKIP')

pkgver()
{
	cd customizepkg-patching
	echo $(git rev-list --count makepkg).$(git rev-parse --short makepkg) # This feels like a makepkg bug to me
}
package()
{
	cd customizepkg-patching
	install -d "$pkgdir/usr/bin"
	sed -i 's/^ver=unknown$/ver='"$pkgver"'/' customizepkg
	install -t "$pkgdir/usr/bin/" customizepkg
	install -d "$pkgdir/etc/customizepkg.d"
}
