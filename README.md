This script aim to ease FreshTomato upgrades by letting users upgrade their FreshTomato router directly from an URL, local storage or from a local server like CIFS/SMB. The script work for both ARM and MIPS devices.

Firmware flashing is no joke and can seriously harm your router, so please review the code before using and use with caution.

I'm not responsible for any bricked devices.

This is still in development and not a finish product.

Any inputs or comments is welcome :)

The "Restore settings" option depends on the Plaintext backup script by @rs232 and need a router that have a USB slot and a USB storage attached to it ;)
To use this option, please refer to @rs232 thread on the linksysinfo.org forum to install the script (script only, the gui is not needed for ftup).

To install and test ftup use these commands: 
```
USERAGENT="Mozilla/5.0 (X11; Linux x86_64; rv:10.0) Gecko/20100101 Firefox/109.0"
alias yget="/usr/bin/wget --no-check-certificate -T 15 -q -U \"$USERAGENT\" --header \"Cache-Control: no-cache\""
yget -O- https://raw.githubusercontent.com/HommeOursPorc/ftup/refs/heads/main/ftup | tr -d "\r" > /tmp/ftup ; chmod +x /tmp/ftup
```

To execute the script, get into the `/tmp` directory and launch the script by typing `ftup`

```
cd /tmp
ftup
```
