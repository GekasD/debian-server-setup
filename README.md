# My Debian server setup

## What is this?
A basic overview of the setup I use to make managing my headless server a bit easier and more fun, currently this includes:
- A packages.txt file containing the names of all the packages I use
- A script/service that makes the motherboard speaker beep when the OS loads

## Installation example
```sh
# Download the files from this repo
git clone https://github.com/GekasD/debian-server-setup.git

# Move to the repo folder
cd debian-server-setup

# Copy files to their correct directories
cp ./lib/systemd/system/startupbeep.service /lib/systemd/system/
cp ./usr/bin/startupbeep.sh /usr/bin/startupbeep.sh

# Make sure startupbeep.sh is executable
chmod +x /usr/bin/startupbeep.sh

# Installing packages from packages.txt using xargs
xargs sudo apt install <packages.txt

# Enable the startup beep script
systemctl enable startupbeep.service
```

You will now hear crazy frog every time your computer boots up, that's crazy!

# Credits
- [ShaneMcC]: Made a repository containing many beep song scripts, visit it [here](https://github.com/ShaneMcC/beeps)
