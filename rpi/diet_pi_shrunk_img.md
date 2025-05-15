# Step one 
`sudo dd if=/dev/{sd card} of={new location for img}`

# Step two

```
sudo touch 1stboot.txt /boot
```

```
@reboot root if [ -e /boot/1stboot.txt ]; then rm /boot/1stboot.txt ; systemctl enable dietpi-fs_partition_resize; /sbin/shutdown -r now ; fi
```

