In order to build a development evironment for website and docker, set a USB disk to pick up Arch Linux and docker installed.

Follow the tutorials:

http://valleycat.org/linux/arch-usb.html

Only a slightly different,when in `pacstrap` change instead

`pacstrap -i /mnt/usb linux linux-firmware base base-devel nano openssh wpa_supplicant dhcpcd ppp dialog netctl sudo`

####### Your first time boot, you need to update, install docker 

`$ sudo pacman -Syu`

`$ sudo pacman -S docker`
    
####### Config auto login and auto wifi

     # Auto login
     ## make directory
    $ sudo mkdir -p /etc/systemd/system/getty@tty1.service.d
    $ sudo nano /etc/systemd/system/getty@tty1.service.d/override.conf

    [Service]
    ExecStart=
    ExecStart=-/usr/bin/agetty --autologin username --noclear %I $TERM

    $ sudo systemctl enable getty@tty1

    # auto start wifi

    # check wifi profile name available

    $ cd /etc/netct
    $ sudo netctl list
    # make a profile accordingly
    # start wifi at boot
    $ sudo netctl enable profile
    $ sudo reboot
