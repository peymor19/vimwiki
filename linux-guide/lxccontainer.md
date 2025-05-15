# Creating LXC Containers

* sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
* yum install epel-release 
* yum install lxc lxc-templates lxc-extra 
* base dir is /usr/share/lxc 
* templates in /usr/share/lxc/templates 

* lxc-checkconfig 

* lxc-create -t download -n lxc-container1 (will ask questions then run the container)
* or 
* lxc-create -t centos -n lxc-centos1 (wont ask questions and run just the centos os)
 

* systemctl start lxc-net -to create lxcbr0 bridge device

* lxc-ls -f -will list containers 
* lxc-start -n <containername>  -F will create an interactive shell 
* lxc-top
* lxc-attach -n <containername>
* lxc-stop <containername> 

* need to autostart lxc container in exam with lxc-autostart
* add lxc.start.auto = 1 in /var/lib/<containername>/config
* echo "lxc.start.auto = 1" >> /var/lib/<containername>/config 
