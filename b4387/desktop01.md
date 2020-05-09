Raspberry Pi B 3 plus as a desktop, finaly you will get 

- a SSH interface to log in other server, it's a basic feature for developer.
- a web browser which we use default Raspbian web browser Chromium, open at boot as kiosk mode.
- an online markdown editor,which require internet connection and web browser. 

At first, we tried to install Raspbian Jessie with a Lxde desktop, a default web browser and a text editor, but there are drawbacks, one is Jessie only come upto versiion number 56 for Chromium browser, another is even I run on Raspbian 8 (Jessie), the RAM has only 1GB, the browser became very slow.It is not only impossible to run Libreoffice at 1GB RAM, but also can not smoothly visit a regular web site.

In order to use Raspberry Pi 3 B Plus as a dektop with only web browser and resonable speed, Raspbiab stretch and kiosk Chromium browser seems a good coice. 

Refer to: https://die-antwort.eu/techblog/2017-12-setup-raspberry-pi-for-kiosk-mode/

The steps are as follows:

