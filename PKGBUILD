# Maintainer: Kamil Stachowski <kamil.stachowski@at@gmail.com>

pkgname=vim-tex_alt-git
pkgver=20121225
pkgrel=1
pkgdesc="Lightweight alternative support for TeX in Vim"
arch=('any')
url="http://www.vim.org/scripts/script.php?script_id=4352"
license=('GPL')
groups=('vim-plugins')
depends=('vim')
makedepends=('git')
optdepends=('ctags' 'snipmate' 'vim-tagbar')
provides=('vim-tex_alt')
conflicts=()
install=vim-tex_alt.install

_gitroot="git://github.com/caminoix/vim-tex_alt.git"
_gitname="vim-tex_alt"

build () {
	msg "Connecting to Git server..."
	if [ -d "$srcdir/$_gitname" ]; then
		cd "$srcdir/$_gitname" && git pull origin || return 1
	else
		git clone "$_gitroot" || return 1
	fi
	msg "Git checkout done or server timeout"
}

package () {
	cd "$srcdir/$_gitname"
	mkdir -p "$pkgdir/usr/share/vim/vimfiles"
	cp -R * "$pkgdir/usr/share/vim/vimfiles/"
	cd "$pkgdir/usr/share/vim/vimfiles/"
	mv "README" "vim-tex_alt-README"
}
