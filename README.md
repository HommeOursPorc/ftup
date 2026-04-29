# FreshTomato Upgrade Script
This script aim to ease FreshTomato upgrades by letting users upgrade their FreshTomato router directly from an URL, local storage or from a local server like CIFS/SMB. The script work for both ARM and MIPS devices.

# Disclaimer
Firmware flashing is no joke and can seriously harm your router, so please review the code before using and use with caution.

I'm not responsible for any bricked devices.

This is still in development and not a finish product.

Any inputs or comments is welcome 🙂

# Installation
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

# Usage
```
FreshTomato Upgrade Script

Usage: ftup [options] [firmware path or URL]

Default is dirty upgrade (NVRAM untouched) unless '-c' is specified.

Single option:
  --changelog      Print latest FreshTomato changelog.
  --check          Print latest FreshTomato version number.
  --erase-nvram    Erase all data in NVRAM memory (thorough).
  --help           Show this message.
  --id             Identify device.
  --list-firmware  List available firmware.
                   Optional: Specify version to list,
                   e.g. --list-firmware 2025.2

Options:
  -a               Auto upgrade to the latest firmware.
  -c               Clean upgrade (no settings restoration).
  -d <path>        Overrides default download directory (/tmp/ftupwd/).
  -f               Force 'unzip on the fly' download mode.
                   This is for devices with low RAM that can't hold
                   both the zip and firmware files in RAM simultaneously).
  -g (ver./build)  Get (download) chosen firmware.
                   Default (no args): Get latest version and same
                   build as the one currently running.
                   Optional: ver. (version), e.g. 2024.4
                   Optional: build, e.g. Mini, Max, VPN, AIO, etc.
                   e.g. -g 2025.2/AIO
  -n               Use wget '--no-check-certificate'
                   (you can try this if wget fail to download the firmware).
  -o               Only download firmware (no installation).
  -y               Automatic 'YES' to prompts. USE WITH CAUTION!
  -z               Force zip download in tmpfs.

Infos:
 - Single option are meant to be run without any other arguments.
 - URL must begin with \"http(s)://\".
 - Supported format is zip, trx, bin and chk.
```
