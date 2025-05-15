# ufw defaults

```
ufw default deny incoming
ufw default allow outgoing
```

# ufw on specific interface

ufw allow in on eth1 to [eth1 ip addr] from [from ip address] port 80 proto tcp

# example
```
ufw allow in on eth1 to any port 22 proto tcp
```
