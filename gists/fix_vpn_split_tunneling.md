
First find you tunnel interface
`netstat -rn | grep default`

```
default  192.168.0.1        en0      ← your normal internet
default  link#35           utun13   ← your VPN
```

Next route only to single ip
`sudo route -n add -host {ip_address} -interface utun13`
