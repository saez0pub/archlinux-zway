# Maintainer: saez0pub saez_pub hotmail com

pkgname=z-way
pkgver=2.0.0
pkgrel=1
pkgdesc="Z-Way communication stack"
arch=('armv6h')
url="http://razberry.z-wave.me"
license=('http://razberry.z-wave.me/docs/ZWAYEULA.pdf')
depends=('v8' 'libarchive' 'libxml2' 'openssl' 'yajl' 'curl'
         'zlib' 'sharutils' 'logrotate')
install=${pkgname}.install
source=("http://razberry.z-wave.me/z-way-server/z-way-server-RaspberryPiXTools-v2.0.0.tgz"
        "http://razberry.z-wave.me/webif_raspberry.tar.gz" "z-way-server.service" "z-way-server.logrotate")

md5sums=('5af9f5cf19e6ed5659a7883b5ce8010f'
         'e930662d01287a9f89c5c69de0dcfaaa'
         '5128c042d184f5b59009123cb577f9d6'
         '9f145dcdf463c9e0f3178fe5ff697d62')


package() {
  mkdir -p ${pkgdir}/etc/z-way
  mkdir ${pkgdir}/opt
  echo "v${pkgver}" > ${pkgdir}/etc/z-way/VERSION
  echo "razberry" > ${pkgdir}/etc/z-way/box_type
  

  tar -zxf z-way-server-RaspberryPiXTools-v${pkgver}.tgz
  mv z-way-server ${pkgdir}/opt/
  install -D -m644 ${srcdir}/z-way-server.service ${pkgdir}/usr/lib/systemd/system/z-way-server.service
  install -D -m644 ${srcdir}/z-way-server.logrotate ${pkgdir}/etc/logrotate.d/z-way-server
  tar -zxf webif_raspberry.tar.gz -C ${pkgdir}/

  #z-way-server compiled with libarchive.so.12
  ln -s /usr/lib/libarchive.so ${pkgdir}/opt/z-way-server/libs/libarchive.so.12
}
