# Linux Commands Playbook

Here, I'll keep adding the necessary linux terminal commands you need to use with your preferred Linux Distribution regularly.

## OpenRGB libi2c and i2c Error fix commands

Yeah I know controlling the RGB components in your Linux PC can be pain in the ar\*\* :/ . Because all the motherboard manufacturer are not comfortable with providing their system controlling software in the linux environment. What an ASS choice :) <br> You can install OpenRGB software in your system and control all the components in your system including RAMs, aRGB fans and strips. I have tested below methods/commands in my Asus ROG Strix motherboard. It works fine for my system, which has four RGB RAMs, six 12v RGB and 5v aRGB fans and 12v RGB strips. <br> Like I said I will be keep updating if I counter any kind of problem in the future.

<strong> 
=> sudo usermod -a -G video USER <br>
=> sudo dnf copr enable name/OpenRGB <br>
=> sudo dnf install openrgb libi2c <br>
=> sudo modprobe i2c_dev <br>
=> sudo openrgb <br>
</strong>

Use apt for debian based system instead of dnf.

<strong>=> sudo dnf search bengali </strong>

You will get multiple options for bengali font. Install your preferred one by running below command.

<strong> => sudo dnf install [...language package name...] </strong>

## Fix for broken Bangla Font in Fedora and Debian based system

### Fedora

First install your preferred Bengali font, I use Kalpurush. Then change the font from the browser and system settings.

You can install Bengali font using Terminal by running this command.

### Debian based System

<strong>
=> sudo apt install fonts-noto-core <br>
=> sudo apt install fonts-noto-ui-core
</strong>

After running above command, remove free-sans and free-serif fonts by running below commands.

<strong>
=> sudo rm -f /usr/share/fonts/truetype/freefont/FreeSans* <br>
=> sudo rm -f /usr/share/fonts/truetype/freefont/FreeSerif*
</strong>

<br>Then clear the font caches and load new fonts.

<strong>=> fc-cache -f -v </strong>

In some cases you may still find broken bengali fonts on Youtube or some other websites. To fix this, just change the font from the browser settings.

## Arch Linux Based System Commands

=> <strong> paccache -r </strong>

Removes the cache of uninstalled packages

=> <strong> sudo pacman -Sy </strong>

Checks for repositories update

=> <strong> sudo pacman -Syu </strong>

Full system update/upgrade command. This command downloads a fresh list for all the installed packages that are out of date. The -y flag forces pacman to download a fresh copy of the package list from the repositories.

=> <strong> sudo pacman -Sc </strong>

Cleans all system wide and old package cache

=> <strong> sudo pacman -Rns </strong>

Removes a package its dependencies and config file backups

=> <strong> sudo pacman -Qtdq </strong>

Checks and lists all the unused and synced dependencies in the system.

=> <strong> sudo pacman -Rns <package-name> </strong>

Removes specific package

=> <strong> sudo pacman -R $(pacman -Qtdq) </strong>

Removes all the unused and synced dependencies from the system.

=> <strong> sudo pacman -Ss <package-name> </strong>

Search for a specific package

=> <strong> sudo pacman -Qs </strong>

Search for installed package in the system

=> <strong> sudo pacman -S pacman-contrib </strong>

=> <strong> sudo pacman verbose </strong>

### Manual installation of AUR packages

First update the system and all repositories

=> <strong> sudo pacman -Syu </strong>

grab the package

$ curl -O <url> (e.g. https://aur.archlinux.org/packages/ya/yaourt/yaourt.tar.gz)

untar package
$ tar xzvf <package.tar.gz>

change into package directory
$ cd <package>

build and install
$ makepkg -si

### JAVA Environments

check status

$ archlinux-java status

set default version

archlinux-java set <version>
