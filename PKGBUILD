# Maintainer: saez0pub saez_pub hotmail com

pkgname=z-way
pkgver=1.7.2
pkgrel=1
pkgdesc="Z-Way communication stack"
arch=('armv6h')
url="http://razberry.z-wave.me"
license=('http://razberry.z-wave.me/docs/ZWAYEULA.pdf')
depends=('v8' 'libarchive' 'libxml2' 'openssl' 'yajl' 'curl'
         'zlib' 'sharutils' 'logrotate')
install=${pkgname}.install
source=("http://razberry.z-wave.me/z-way-server/z-way-server-RaspberryPiXTools-v1.7.2.tgz"
        "http://razberry.z-wave.me/webif_raspberry.tar.gz" "z-way.service" "z-way-server.logrotate")

md5sums=('cf19954c94271ea0206fe1b28120262e'
         'e930662d01287a9f89c5c69de0dcfaaa'
         'd41c61c7034ca7d48433a4798f3ace64'
         '9f145dcdf463c9e0f3178fe5ff697d62')


package() {
  mkdir -p ${pkgdir}/etc/z-way
  mkdir -p ${pkgdir}/opt
  echo "${pkgver}" > ${pkgdir}/etc/z-way/VERSION
  echo "razberry" > ${pkgdir}/etc/z-way/box_type
  

  tar -zxf z-way-server-RaspberryPiXTools-v${pkgver}.tgz
  mv z-way-server ${pkgdir}/opt/
  install -D -m644 ${srcdir}/z-way-server ${pkgdir}/usr/lib/systemd/system/z-way-server.sevice
  install -D -m644 ${srcdir}/z-way-server.logrotate ${pkgdir}/etc/logrotate.d/z-way-server
  tar -zxf http://razberry.z-wave.me/webif_raspberry.tar.gz -C ${pkgdir}/
}
