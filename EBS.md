
show all ebs
lsblk

Format a disk to use
mkfs.ext4 /dev/xvdb

create a file:
sudo mkdir test
sudo su > cd /

Mount:
mkfs.ext4 /dev/xvdb

Check
mkfs.ext4 /dev/xvdb

unmount:
umount /test/

Remount the dir after the Instance restarts

/etc/fstab
Then
<disk path> <folder path> <filesystem type> etc

It reads the beginning of the raw disk partition /dev/xvda1

sudo file -s /dev/xvda1
