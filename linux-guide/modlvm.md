# Extending Volume Groups and Logical Volumes

* ext can be shrunk xfs cannot be shrunk 

* to extent logical volumes look at examples of lvextend man pages

* make new partition the size that you are trying to extend 
* partprobe 
* lsbllk to check if partition is available 
* pvcreate to create phyical volume 
* vgextendwill create phyical volume automatically 
* vgextend /dev/<volumegroupnamethatyouaretryingtoextend> /dev/<newphyicalgroup>
* lvextend -r(resize filesystem) -L +2G /dev/vgdata/lvdata to extend. Change names to you specific setting
           ^^(can also use resize2fs)
