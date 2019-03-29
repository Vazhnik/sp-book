## Linux Uptime
uptime

### /proc/uptime (https://askubuntu.com/a/335699)
/proc/uptime pseudo-file contains two numbers:
- The first number is how long the system has been up in seconds.
- The second number is how much of that time the machine has spent idle in seconds. (On multi core systems, this is accumulated on a per CPU basis.) 

Example:<br>
`awk '{print int($1/3600)":"int(($1%3600)/60)":"int($1%60)}' /proc/uptime`

