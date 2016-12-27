# MioMenuQ
MioMenuQ is an alternative to your default applcation and is based on apps like 
SystemInformation by Daniel Schumann, Moov Settings, MortScript, [AutoMount](https://github.com/karasq/automount) 
and reset.exe.

This application was tested on **Mio Spirit 6970 LM** running on Windows CE 6.0 operating 
system with default Navman application, so it's addressed to owners of this device.

![alt text](https://github.com/karasq/MioMenuQ/raw/master/UI/screen.png "MioMenuQ Screen")

## Installation

1. Connect your device to PC.
2. *Update your default software to the newest version through MioMore Desktop.
3. *Make a backup of your device through MioMore Desktop.
4. Copy `Menu` folder to `Program Files\` direcotry on your device.
5. Copy file `Program Files\Navman\appstartupsec.ini` to `Program Files\Navman\appstartupsec.bak.ini` on your device.
6. Append following lines to `Program Files\Navman\appstartupsec.ini` on your device:
   ```ini
[Process9]
RelativePath=FALSE
ProcessFile=Program Files\Menu\startmenu.exe
DefaultCmdLine=
BootCmdLine=
StartOnBoot=1
MaxRestarts=0
TreatCloseAsError=FALSE
Major=TRUE
WindowName=Startmenu
MaxCloseMessages=10
KeysToForward=0x7A,0xC4
KeysToBoot=
```
   Just make sure there is no other section called `[Process9]`. If so, then change it to e.g. `[Process10]`.

7. Disconect your device from PC. Power off your device and power on it again. 
Now menu should start instead of default application.

**Points 2 and 3 are not required but highly recommended.*

## Configuration

By default this menu is conigured like this:

1. Mio icon will run application located at `\My Flash Disk\Program Files\Menu\startmio.exe`.
   This appliaction will start [startmio.mscr](https://github.com/karasq/MioMenuQ/blob/master/Menu/startmio.mscr) 
   that will kill menu and start default Mio application.

2. AutoMap icon is configured to run application located at `\Storage Card\AutoMapa EU\AutoMapa EU.exe`.
3. Power Off icon is configured to run application located at `\My Flash Disk\Program Files\Menu\poweroff.exe`.
   This application will start [poweroff.mscr](https://github.com/karasq/MioMenuQ/blob/master/Menu/poweroff.mscr) 
   that will sleep your device.

4. Windows icon is configured to run application located at `\Windows\explorer.exe`.
   This will start built-in Windows Explorer.

5. Settings icon is configured to run application located at `\My Flash Disk\Program Files\Menu\Moov Settings\Settings.exe`.
   This will start Moov Settings application that let you configure your device (date, backlight, sound volume level, etc)

6. Reset icon is configured to run application located at `\My Flash Disk\Program Files\Menu\restart.exe`.
   This will reboot your device.

To change menu default configuration please take a look to [desktop.ini](https://github.com/karasq/MioMenuQ/blob/master/Menu/desktop.ini).

AutoMount application located at `\My Flash Disk\Program Files\Menu\automount.exe` will be start before Menu. 
Mio Spirit 6970 LE doesn't mount SD card partition during booting process. This application will mount available, 
unmouted partitions, so location `\Storage Card\` will be available without manually reinserting memory card.

## Known issues

1. Your device will be not detected by PC when you run Menu. You need to connect your device to PC and 
then restart your device or disconect your device from PC and start Mio application and then connect it again.

## Disclaimer
Wrong usage of this application, insalling it on untested models may cause permanent dameage like 
lossing access to your device. You are using this software at your own risk.