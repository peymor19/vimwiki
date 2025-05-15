# Shell shortcuts

| command | result                  |
| ------- | ----------------------- |
| ctrl-a  | beginning of line       |
| ctrl-e  | end of line             |
| ctrl-p  | previous search history |
| ctrl-n  | next search history     |
| ctrl-b  | moves cursor backwards  |
| ctrl-f  | moves cursor forwards   |
| ctrl-f  | applys auto suggestion  |
| alt-f   | applys auto suggestion one word at a time|


## Want to write a document as sudo??
| command        | result                                    |
| -------------- | ----------------------------------------- |
| :w !sudo tee % | writes as sudo if you are normal user     |

## Add sudo to Previous command
| command | result                 |
| ------- | ---------------------- |
| "ALT" s | Apends sudo to command |


# Disable lap mode and force performance power management for laptops
```
echo performance | sudo tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor
```
