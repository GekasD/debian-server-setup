# My Debian server setup

## What is this?
A basic overview of the setup I use to make managing my headless server a bit easier and more fun, currently this includes:
- A packages.txt file containing the names of all the packages I use
- A systemd service that makes the motherboard speaker beep when the OS loads (by calling a script file)

## Installation example
You can switch to the root user (using `sudo su`), if you don't want to type sudo for most of these
```sh
# Download the files from this repo
git clone https://github.com/GekasD/debian-server-setup.git

# Move to the repo folder
cd debian-server-setup

# Downloading a bunch of beep songs inside our directory
git clone https://github.com/ShaneMcC/beeps.git

# Copy systemd service file to it's correct directory
sudo cp ./services/startupbeep.service /lib/systemd/system/

# Create an empty sh file on /usr/bin called startupbeep.sh, and make it executable
sudo touch /usr/bin/startupbeep.sh
sudo chmod +x /usr/bin/startupbeep.sh

# Append the content of a beep script inside startupbeep.sh using cat, for example:
sudo cat ./beeps/mario-victory.sh > /usr/bin/startupbeep.sh

# Installing packages from packages.txt using xargs
xargs sudo apt install <packages.txt

# Enable the startup beep script on boot
systemctl enable startupbeep.service
```

You will now hear the mario victory theme every time your computer boots up, that's crazy!

# Credits
- [ShaneMcC]: Made a repository containing many beep song scripts, visit it [here](https://github.com/ShaneMcC/beeps)