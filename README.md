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
5. Copy file `Program File\Navman\appstartupsec.ini` to `Program File\Navman\appstartupsec.bak.ini` on your device.
6. Append following lines to `Program File\Navman\appstartupsec.ini` on your device:
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

## Disclaimer
Wrong usage of this application, insalling it on untested models may cause permanent dameage like 
lossing access to your device. You are using this software at your own risk.