# My Debian server setup

## What is this?
A basic overview of the setup I use to make managing my headless server a bit easier and more fun, currently this includes:
- A packages.txt file containing the names of all the packages I use
- A script/service that makes the motherboard speaker beep when the OS loads

## Installation
```sh
# Download the files from this repo and put them in their correct directories

# Installing packages from packages.txt using xargs
xargs sudo apt install <packages.txt

# Make sure startupbeep.sh is executable
chmod +x /usr/bin/startupbeep.sh

# Enable the startup beep script
systemctl enable startupbeep.service
```

You will now hear crazy frog every time your computer boots up, that's crazy!