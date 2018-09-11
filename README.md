# raspberrypi-startup
Standard routine to setup my raspberryPi

## Etch Image
1. Download newest image
2. Use Etcher to etch image on SD card

## Enable SSH
1. open terminal
2. cd into the SD card
3. cd /Volumes/boot
4. create at ssh file to enable ssh
5. touch ssh

## SSH into the Pi
1. search IP address of pi
2. ssh pi@xxx.xxx.xxx.xxx
3. password = raspberry
4. change password
5. passwd (enter new password twice)

## Update and Upgrade
1. sudo apt-get update
2. sudo apt-get upgrade

### If there is a problem with changed ssh user
ssh-keygen -R 192.xxx.xxx.xxx
This will flush all the saved ssh keys for your user

### List connected hardware
lsusb

### Install FTP
sudo apt-get update
sudo apt-get install vsftpd
sudo nano /etc/vsftpd.conf

Add to vsftpd.conf File:
anonymous_enable=NO
local_enable=YES
write_enable=YES
local_umask=022
chroot_local_user=YES
user_sub_token=$USER
local_root=/ 

sudo service vsftpd restart
