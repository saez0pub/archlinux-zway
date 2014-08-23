## Installation ##
```
mkdir /tmp/z-way
cd /tmp/z-way/
git clone git@github.com:saez0pub/archlinux-zway.git
cd archlinux-zway/
makepkg
sudo pacman -U ./z-way-1.7.2-1-armv6h.pkg.tar.xz
```

## How to run ##
systemctl start z-way-server

open the http://IP:8083 interface with IP as the IP address of the rasbperry pi
