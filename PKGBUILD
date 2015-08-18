#Maintainer: Reuben Castelino <projectdelph[at]gmail[dot]com>
pkgname=ytr
pkgver=20120826
pkgrel=1
pkgdesc="A shell script that streams youtube audio to the command line through vlc"
url='https://github.com/projectdelphai/ytr'
arch=('any')
license=('GPL')
depends=('vlc' 'ruby' 'ruby-highline' 'ruby-httparty')

_gitroot='git://github.com/projectdelphai/ytr.git'
_gitname='ytr'

build() {
  cd "${srcdir}"
  msg 'Connecting to GIT server....'

  if [ -d "${_gitname}" ] ; then
    cd "${_gitname}" && git pull origin
    msg 'The local files are updated.'
  else
    git clone "${_gitroot}" "${_gitname}"
  fi

  msg 'GIT checkout done or server timeout.'
}

package() {
  cd "${srcdir}/ytr"
  install -Dm755 ${pkgname} ${pkgdir}/usr/bin/${pkgname}
}
