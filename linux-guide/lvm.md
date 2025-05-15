# LVM

* first need pysical volume. Either Disk, partition or RAID device 

* physical volume -> Volume group -> Logical volume

* must set partition type

* pvcreate 
* vgcreated 
* lvcreate
* mkfs
* mount/fstab 
* examn grades for surviving reboot. Must use fstab

* fdisk /dev/sd<unusedletter> 
* command m for help 
* n for new partition
* p for primary
* 1 for part number 
* default first sector 
* last sector +<amount>G
* p for print to view status
* t to change partition ID 
           ^^^defualt partition ID is 8e
* w to write config 
* veryify it is usable by using lsblk
 
* pvcreate /dev/<partition name>
* pvs will show all phyical volumes
 
* vgcreate <volumegroupname> <devices> <devices>
* use man pages to see examples 

* vgs shows volume groups 
* vgdisplay detailed ^

* lvcreate -n <name> -L <size>G /dev/<volumegroup>
* lvs shows logical volumes  

* mkfs.ext4 /dev/v<volumegroup>/<logicalvolume>
 
* finally put in fstab to survive boot
* /dev/<volumegroup>/<lvm>      /data    ext4   defaults   0 0 
								^this is where it is suposed to be mounted 
* mkdir /data 
	
* mount -a to mount all in fstab that hasnt been mounted yet
