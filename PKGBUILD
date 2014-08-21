# Maintainer: saez0pub saez_pub hotmail com

pkgname=z-way
pkgver=1.7.2
pkgrel=1
pkgdesc="Z-Way communication stack"
arch=('armv6')
url="http://razberry.z-wave.me"
license=('http://razberry.z-wave.me/docs/ZWAYEULA.pdf')
depends=('v8','libarchive','libxml2','openssl','yajl','curl','zlib','sharutils','logrotate')
install=${pkgname}.install
source=("http://razberry.z-wave.me/z-way-server/z-way-server-RaspberryPiXTools-v1.7.2.tgz"
        "http://razberry.z-wave.me/webif_raspberry.tar.gz","z-way.service","z-way-server.logrotate")
md5sums=('195960e048bfa77badc2a3df382a5a88'
         'a2a8a3ee7018d5681403088dcd3d2c2e'
         '9419012794e5e134bc152cfd388d63e7'
         '3be05b06c7a6e269d9a4c74dcf239d19')

build() {

}

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
