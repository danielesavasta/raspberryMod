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

## Waveshare 7" screen
add this to the end of the config.txt
#overscan to adjust image position
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0

#set current over USB to 1.2A
max_usb_current=1

#HDMI config
hdmi_drive=1
hdmi_ignore_edid=0xa5000080
hdmi_group=2
hdmi_mode=87

#1024x600 display
hdmi_cvt=1024 600 60 3 0 0 0

#LAUNCH.SH
cd ~/processing-3.4/
DISPLAY=:0 ./processing-java --sketch=/home/pi/app --present

#give execution permission
chmod +x /home/pi/Desktop/launch.sh

#add a crontab job
sudo crontab -e
@reboot /home/pi/Desktop/launch.sh
