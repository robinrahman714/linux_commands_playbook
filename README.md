# Linux Commands Playbook

Here, I'll keep adding the necessary linux terminal commands you need to use with your preferred Linux Distribution regularly.

## OpenRGB libi2c and i2c Error fix commands

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
