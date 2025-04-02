# Ubuntu Installation Guide 

## Code Formatting Guidelines
- https://www.youtube.com/watch?v=-J3wNP6u5YU
- https://www.youtube.com/watch?v=CFRhGnuXG-4
- https://www.youtube.com/watch?v=hxGOiiR9ZKg
- https://www.youtube.com/watch?v=rQlMtztiAoA
- https://www.youtube.com/watch?v=tD5NrevFtbU
- https://www.youtube.com/watch?v=wSDyiEjhp8k

## Things to do:

### Necessary
- In order to install Ubuntu in the first place, you need to: find a drive that hasn't been corrupted; format it or use a tool like Ventoy (with Ventoy you flash the drive then drag the iso into the partition and with Rufus or Balena Etcher you can just flash directly); create an empty space that is large enough for everything (300gb ideally); boot into the UEFI menu to disable secure boot, turn on Compatibility Support Module (CSM), disabling fast boot, and changing the boot order to use the USB; installing Ubunut onto the empty space by creating a partition from the empty space, setting its root to "/," and leaving behind 5MB for the bios reserved boot partition; and finally creating a user and restarting.
- Check your graphics drivers by runnning `sudo lshw -c video` and seeing if it matches (should show NVIDIA if using an NVIDIA gpu).
- If it isn't correct run `sudo ubuntu-drivers devices` and installing the corresponding graphics drivers with `sudo apt-get install nvidia-driver-<version_number>`.

Install the following:
- ROS
- IDE (VSCode is convenient)
- Git
- Github CLI (unless you want to setup an SSH token)
- Github Desktop

### Personal
- Install a theme (e.g., Catppuccin or Dracula)
- Change the wallpaper to something interesting
- Use GNOME extensions to move the taskbar to the bottom
- Modify the system fonts and terminal
- Install neofetch
- Configure neovim
- Installing webdev and ML tools


Enabling other apt repos
```bash
sudo add-apt-repository universe
sudo add-apt-repository restricted
sudo add-apt-repository multiverse
sudo apt update
```

VSCode Install
```bash
sudo apt-get install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" |sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null
rm -f packages.microsoft.gpg
sudo apt install apt-transport-https
sudo apt update
sudo apt install code
```