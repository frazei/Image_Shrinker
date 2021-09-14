A simple script to shrink a image of unwanted free space.

***
https://www.raspberrypi.org/forums/viewtopic.php?t=111531

The awk offset for the sector size was wrong. I replaced the line....

SECTOR_SIZE=$(fdisk -l $IMAGEFILE | grep 'Units' | awk '{print $9}')

with

SECTOR_SIZE=$(fdisk -l $IMAGEFILE | grep 'Units' | awk '{print $8}')

also the hardcoded /dev/loop0 should be replaced with $LOOP_DEV in lines 128,132 and 136
