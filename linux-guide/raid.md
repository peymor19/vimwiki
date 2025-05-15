# RAID

* lsblk - shows all mass storage devices and partitions
* mdadm package for RAID
 
* use examples on man pages. 
* mdadm --create /dev/md0 --level=1 --raid-devices=2 /dev/hd[ac]1 
 
* After setting up RAID. Next make filesystem on the RAID disk. 
 
* mkfs.xfs /dev/md0 

* mkdir /raid 

* Edit fstab. vim /etc/fstab
* /dev/md0       /raid     xfs    defaults   0  0 

* mount -a (a is mount all that is not mounted right)

# RAID LEVELS
* 0. 2 disks. Improves performace and storage but no fault tolerance. 

* 1. 2 disks. Fault tolerance for one drive failure. Basically mirrored drives.

* 5. 3 disks. Highest read rate. Meduim write rate. One drive failure ok. 2 drive failure = data loss

* 10. 4 disks. Combination of level 0 and 1. Striping and mirrored. Data can be retrived as long as one drive is still funcitonal. 
