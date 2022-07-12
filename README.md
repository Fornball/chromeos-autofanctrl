# chromeos-autofanctrl
Chromeos fan control script, for chromebooks with fan speed problems.
## Description
When my Asus Flip CX5 chromebook gets hot, it spins up its fans. After a while the chromebook cools down, but the fans keep spinning at 60% speed, even with the cpu at 40°C. 
This script resets the fan control every 5 seconds, so the fans function as intended. 
The install script will create a new directory under /usr/local/ and download all the required files. Then it will setup a service that runs on startup and executes the command ```sudo ectool autofanctrl``` every 5 seconds. From my testing this script has absolutely no impact on the system, except making the fans behave correctly.
## Read before installing
This script requires the chromebook to be in developer mode. It will also disable boot verfication and remount the system partition as read/write. This is needed to modify the system and add a new service to it. However this **will make the system more insecure**. To be precise this will make the system **as secure as a regular linux installation**(so still pretty secure). Do your own research if you are unsure about this.
## Installation
1. Chromebook must be in [developer mode](https://www.androidauthority.com/how-to-enable-developer-mode-on-a-chromebook-906688/).
2. Press ctrl+alt+t to open the terminal, then type ```shell``` and press enter.
3. Paste ```sudo curl -L "https://raw.githubusercontent.com/apacelus/chromeos-autofanctrl/main/install.sh" | sudo bash``` into terminal and press enter.
4. After the chromebook reboots run ```sudo curl -L "https://raw.githubusercontent.com/apacelus/chromeos-autofanctrl/main/install.sh" | sudo bash -s -- -rebooted``` in the terminal.
## Post-install
The script needs to be reinstalled after every update.
## Todo:
- [ ] Reinstall automatically after system update