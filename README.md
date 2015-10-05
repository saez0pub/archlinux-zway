## Installation ##
```
yaourt -Sy mongoose v8 libxml2 sharutils
*Edit mongoose' PKGBUILD and change arch to 'any'
mkdir /tmp/z-way
cd /tmp/z-way/
git clone git@github.com:saez0pub/archlinux-zway.git
cd archlinux-zway/
makepkg
sudo pacman -U ./z-way-*.pkg.tar.xz
```

## How to run ##
systemctl start z-way-server

open the http://IP:8083 interface with IP as the IP address of the rasbperry pi
