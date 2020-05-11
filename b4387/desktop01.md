The features achieved should be 

- a SSH interface to log in other server, it's a basic feature for developer.
- a web browser which we use default Raspbian web browser Chromium, open at boot as kiosk mode.
- an online markdown editor,which require internet connection and web browser. 

At first, we tried to install Raspbian Jessie with a Lxde desktop, a default web browser and a text editor, but there are drawbacks, one is Jessie only come upto versiion number 56 for Chromium browser, another is even I run on Raspbian 8 (Jessie), the RAM has only 1GB, the browser became very slow.It is not only impossible to run Libreoffice at 1GB RAM, but also can not smoothly visit a regular web site.

In order to use Raspberry Pi 3 B Plus as a dektop with only web browser and resonable speed, Raspbiab stretch and kiosk Chromium browser seems a good coice. 

Refer to: https://die-antwort.eu/techblog/2017-12-setup-raspberry-pi-for-kiosk-mode/

The steps are as follows:

Step 1: Download raspbian stretch and flash to minicard which Raspberry Pi use. 

Write to minicard with balenaEtcher on Windows.

Step 2: Boot the Raspberry Pi, log in as user 'pi' and password 'raspberry', run $ sudo raspi-config,

- Localisation Options: Select your preferred locale timezone, and keyboard layout.
- Boot Options: Select “Desktop / CLI” and then “Console Autologin”. 
- Interfacing Options: Enable SSH access if needed.

update

Run $ sudo apt update

You will get a SSH and a Command Line inetrface. 

Step 3: Install required softwares.

Run $ sudo apt-get install --no-install-recommends xserver-xorg x11-xserver-utils xinit openbox

$ sudo apt-get install --no-install-recommends chromium-browser

Step 4: Edit the kiosk mode.

$ sudo nano /etc/xdg/openbox/autostart

    # Disable any form of screen saver / screen blanking / power management
    xset s off
    xset s noblank
    xset -dpms

    # Allow quitting the X server with CTRL-ATL-Backspace
    setxkbmap -option terminate:ctrl_alt_bksp

    # Start Chromium in kiosk mode
    sed -i 's/"exited_cleanly":false/"exited_cleanly":true/' ~/.config/chromium/'Local State'
    sed -i 's/"exited_cleanly":false/"exited_cleanly":true/; s/"exit_type":"[^"]\+"/"exit_type":"Normal"/' ~/.config/chromium/Default/Preferences
    chromium-browser --disable-infobars --kiosk 'http://your-url-here'
    # Caution:
	# You can set url like 'https://www.google.com' or 'about:blank' whatever you want to open.
    # Exit kiosk mode with CTRL-ATL-Backspace
    # Restart with 'startx' in command line interface.
    
Step 5: startx automatically on boot

`$ sudo nano .bash_profile`, add the following content then save.
	
	[[ -z $DISPLAY && $XDG_VTNR -eq 1 ]] && startx

 Next time,reboot computer, you will get a koisk moder browser open automatically on boot, when browser open and load, just click Ctrl-N to open a new window.

Step 6: Use online editor

Use http://prose.io to edit contents integrated with your github.com account.
