# Groups/Users/ACLS

# Group

* groupadd 
* mkdir -p(make parent dir as well) /data/<group>
* chgrp <group> <file> 
* chmod 1770 <file> or chmod +t <file> to make sticky bit

# User

* useradd <user>
* chown <user> <file>

# User Permissions
* check bashrc for umask permission
* umask subtracts from default permisions 

* FILES DEFAULT - 666
* FOLDERS DEFAULT - 777
* DEFULAT UMASK non root - 002      like 666-002 = 664 rw-rw-r--



# ACL

* setfacl -m  <d>:<g/u>:<group/user>:<rwx> <file>
              ^(sets acl to all new files created as well)
* can also use -R for recursive if dir
