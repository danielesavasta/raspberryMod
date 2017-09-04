# raspberryMod
Common changes for raspberry pi

##Fixing mouse speed
sudo nano /boot/cmdline.txt
add this to the end of the cmdline: usbhid.mousepoll=0
save & reboot

##Update
sudo apt-get update
sudo apt-get dist-upgrade

##node
update-nodejs-and-nodered

### add node at the startup
/etc/rc.local
su pi -c 'node /home/pi/server.js < /dev/null &'
