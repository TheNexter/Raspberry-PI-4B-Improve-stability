# Raspberry-PI-4B-Improve-stability


For your OS > **Never ubuntu, use raspberry pi os**

For raspberry pi os, install raspberry pi os 64 bit lite **ON MICRO SD CARD**, if you have SSD, just save them for you docker container config.

After you install the os and update them and restart them do this >

sudo nano /boot/config.txt

add at the bottom >

dtoverlay=disable-wifi
dtoverlay=disable-bt

save and restart

With that you block wifi and bluetooth, i don't know why but help for stability for my server (before disconnect from ethernet every day)


if you want to mount your ssd ou disk on you machine >

format disk with >

list disk >
lsblk --fs

in my case sda is my disk
sudo mkfs -t ext4 /dev/sda

now i create folder where to mount the disk :
mkdir /home/pi/mysuperdisk

sudo nano /etc/fstab

add this line at the bottom

UUID=find them with lsblk --fs                                      /home/pi/mysuperdisk        ext4     defaults     0     2

save and reboot and good
