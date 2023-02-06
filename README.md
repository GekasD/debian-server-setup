# My Debian server setup

## What is this?
Scripts that make managing my headless server a bit easier and more fun, currently only a startup beep script is included.

## Installation
```sh
# Download the files from this repo and put them in their correct directories

# Make sure startupbeep.sh is executable
chmod +x /usr/bin/startupbeep.sh

# Install 'beep'
sudo apt install beep

# Enable the startup beep script
systemctl enable startupbeep.service
```

You will now hear crazy frog every time your computer boots up, that's crazy!