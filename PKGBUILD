# Contributor: Spider.007 <archlinux AT spider007 DOT net>

pkgname=stem-git
pkgver=20130328
pkgrel=1
pkgdesc="Python controller library for Tor"
arch=('i686' 'x86_64')
url="https://stem.torproject.org/"
license=('LGPL3')
makedepends=('git')
optdepends=('tor: you need a tor-server to talk to')

_gitroot=('https://git.torproject.org/stem.git')
_gitname=('stem')

build() {
  cd $srcdir
  msg "Connecting to githup.com GIT server...."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin && cd ..
    msg "Updated local checkout"
  else
    git clone $_gitroot
  fi

  cd $srcdir/$_gitname
  python setup.py install --root="$pkgdir/" --optimize=1
}
