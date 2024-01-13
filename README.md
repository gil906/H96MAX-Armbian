# H96MAX Armbian

This is an Armbian Debian Bullseye Image for the H96 MAX TV Box.

***I assume no liability for any damage caused by changing the software.***


Installation video
https://youtu.be/uuOujI-yfYU

## Self-created image
Download:
https://drive.google.com/file/d/1nU2_yQY3Oh7GQYWXxNAR4u5qr25xtTLU/view?usp=share_link

Image created with the following parameters
```
./compile.sh BOARD=rk3318-box BRANCH=current RELEASE=bullseye BUILD_MINIMAL=yes BUILD_DESKTOP=no KERNEL_ONLY=no KERNEL_CONFIGURE=no COMPRESS_OUTPUTIMAGE=sha,gpg,img
```

## The image of jock
https://users.armbian.com/jock/rk3318/

Download:
https://users.armbian.com/jock/rk3318/Armbian_22.05.0-trunk_Rk3318-box_bullseye_current_5.15.35_minimal.img.xz

armbian forum thread by jock
https://forum.armbian.com/topic/24085-csc-armbian-for-rk3318rk3328-tv-box-boards/


## Multi-tool
https://users.armbian.com/jock/rk3318/multitool.img.xz
https://drive.google.com/file/d/1YUOc95bJbCM8Tq44plZ0q1DeJW8-gDE7/view?usp=share_link

## Commands from the video
rk3318-config
```
rk3318-config
```
Update packages
```
apt update
```
Install armbian-config
```
apt install armbian-config
```
armbian-config
```
armbian-config
```
Update packages
```
apt upgrade
```

Display IP address
```
ip a
```

Restart computer
```
reboot
```

change password
```
passwd
```

Configure WiFi
```
nmtui
```

## alternatively the WiFi drivers for the 2734C chip
```
cd ~
```
```
wget https://raw.githubusercontent.com/blacknet76/H96MAX-Armbian/main/brcmfmac4334-sdio.rockchip%2Crk3318-box.txt
```
```
sudo cp /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.bak
```
```
sudo cp brcmfmac4334-sdio.rockchip,rk3318-box.txt /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt
```

Now we prevent the file from being overwritten by the Update Manager
```
sudo chattr +i /lib/firmware/brcm/brcmfmac4334-sdio.rockchip,rk3318-box.txt
```

Restart computer
```
sudo reboot
```

Then configure the WLAN with
```
nmtui
```

IP queries
```
ip a
```
Restart box
```
sudo reboot
```

Configure WiFi
```
nmtui
```

IP queries
There should now be an IP address under wlan0
```
ip a
```

Reboot and see if everything works
