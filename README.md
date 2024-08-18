# Linux Commands Playbook

Here, I'll keep adding the necessary linux terminal commands you need to use with your preferred Linux Distribution regularly.

## OpenRGB libi2c and i2c Error fix commands

=> sudo usermod -a -G video USER
=> sudo dnf copr enable name/OpenRGB
=> sudo dnf install openrgb libi2c
=> sudo modprobe i2c_dev
=> sudo openrgb

Use apt for debian based system instead of dnf.

=> sudo dnf search bengali

You will get multiple options for bengali font. Install your preferred one by running below command.

=> sudo dnf install [...language package name...]

## Fix for broken Bangla Font in Fedora and Debian based system

### Fedora

First install your preferred Bengali font, I use Kalpurush. Then change the font from the browser and system settings.

You can install Bengali font using Terminal by running this command.

### Debian based System

=> sudo apt install fonts-noto-core
=> sudo apt install fonts-noto-ui-core

After running above command, remove free-sans and free-serif fonts by running below commands.

=> sudo rm -f /usr/share/fonts/truetype/freefont/FreeSans*
=> sudo rm -f /usr/share/fonts/truetype/freefont/FreeSerif*

Then clear the font caches and load new fonts.

=> fc-cache -f -v

In some cases you may still find broken bengali fonts on Youtube or some other websites. To fix this, just change the font from the browser settings.
