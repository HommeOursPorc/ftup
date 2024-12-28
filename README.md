Work In Progress. Test at your own risk. Only sharing my progress for the moment.

make sure you know how to recover a bricked router :p

To install and test use these commands: 
```
USERAGENT="Mozilla/5.0 (X11; Linux x86_64; rv:10.0) Gecko/20100101 Firefox/109.0"
alias yget="/usr/bin/wget --no-check-certificate -T 15 -q -U \"$USERAGENT\" --header \"Cache-Control: no-cache\""
yget -O- https://raw.githubusercontent.com/HommeOursPorc/ftup/refs/heads/main/ftup | tr -d "\r" > /tmp/ftup ; chmod +x /tmp/ftup
```
