# Step One

Make sure dietpi and light are added to the dialout group to connect to a device using stty

Make sure the IP address is set to static



Create this file
```
sudo touch /boot/1stboot.txt
```


Add this into `/etc/crontab`
```
@reboot root if [ -e /boot/1stboot.txt ]; then rm /boot/1stboot.txt ; /usr/bin/raspi-config --expand-rootfs ; /sbin/shutdown -r now ; fi
```

Copy cleanup script from gitlab and run as sudo

```
sudo ./cleanup.sh
```

# Step Two

Remove the sd card from the SBC and insert it into your PC
```
sudo dd if=/dev/{sd card} of={new location for img}
```

# Step Three

Use cotsworldjam script to shrink the image

```
raspbian-shrink imagename.img [output.img]
```

# Step Four

Compress the shrunken img

```
tar -cJf output.img.tar.xz shrunkenimg.img
```

# Step Five

create a sha 256 check sum

```
sha256sum imagename.img.tar.xz > checksum.txt
```

# Step Six

Create a detached GPG signature

```
gpg --local-user {USER} --output imagename.img.tar.xz.sig --detach-sign imagename.img.tar.xz
```

# How to verify a checksum

```
sha256sum -c checksum.txt
```

# How to veryify a GPG signature

```
gpg --verify imagename.img.tar.xz.sig
```
