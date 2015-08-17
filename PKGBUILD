# Contributors: Sirius Bakke <sirius\at/nonline.org>
#               roughl
pkgname=pam_mount
pkgver=2.13
pkgrel=3
pkgdesc="A PAM module that can mount volumes for a user session"
arch=('i686' 'x86_64')
url="http://pam-mount.sourceforge.net/"
license=('GPL')
depends=('util-linux' 'libhx>=3.12.1' 'libxml2>=2.6' 'openssl>0.9.7' 'cryptsetup>=1.1.2')
optdepends=('hxtools: If you have something like <logout wait="1000" hup="0" term="1" kill="1" /> in your config' )
backup=('etc/security/pam_mount.conf.xml')
options=(!emptydirs)
source=("http://downloads.sourceforge.net/project/pam-mount/$pkgname/$pkgver/$pkgname-$pkgver.tar.xz")
md5sums=('9f75fc8e84ea9cde619cdd6a62c7de33')

build() {
  cd -- "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --with-ssbindir=/usr/sbin --with-slibdir=/usr/lib --sysconfdir=/etc --localstatedir=/var
  make
}

package() {
  cd -- "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}

