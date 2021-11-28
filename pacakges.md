sudo
git
zsh
xf86-video-intel
xmonad
xmonad-contrib
xmobar
dmenu
noto-fonts-cjk
noto-fonts
ttf-dejavu
alacritty
picom
trayer
volumeicon
network-manager-applet
feh
ranger
grub
efibootmgr
sddm
scrot
xrog-xrdb
xorg-xrandr
xorg-xdpyinfo
linux-headers
broadcom-wl-dkms
pcmanfm
xdg-utils
otf-font-awesome

**yay**
libxft-bgra-git
ttf-apple-emoji

## drive bcm4360 for archlinux

### step 1
edit`/etc/modprobe.d/broadcom-wl-dkms.conf`
```shell
blacklist b43
blacklist b43legacy
blacklist bcm43xx
blacklist bcma
blacklist brcm80211
blacklist brcmfmac
blacklist brcmsmac
blacklist ssb
```

### step 2
```shell
pacman -Syu linux-headers broadcom-wl-dkms
mkinitcpio -p linux
```
at last, restart

## Intel Graphics
solusion for screen tearing
edit `/etc/X11/xorg.conf.d/20-intel.conf
```shell
Section "Device"
  Identifier "Intel Graphics"
  Driver "intel"
  Option "DRI" "2"
  Option "AccelMethod" "sna"
  Option "TripleBuffer" "true"
  Option "TearFree" "true"
EndSection
```
