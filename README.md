# OpenCore_Asus_X441UV
OpenCore EFI settings for Asus X441UV

![asusx441uv](https://www.asus.com/media/global/gallery/vxJCXiQvvDJIPwmt_setting_fff_1_90_end_500.png)

## Introduction
Hackintoshing is not user-friendly for beginner (in my personal experience). If you are not familiar with OS installation and such, please consider to try installing linux first and use it for some time. This project aims to simplify post-installation EFI setup for Asus X441UV user.

## Instruction
Clone or download  
Install MacOS with your preferred method. [Olarila Clover Vanilla](https://www.olarila.com/topic/5794-hackintosh-guide-install-macos-with-vanilla-olarila-image-step-by-step-install-and-post-install-windows-linux-or-mac/) for easy steps, but in step 7 afterward just copy this repo EFI folder instead of Olarila EFI folder.   
Mount EFI drive. You can use [MountEFI](https://github.com/corpnewt/MountEFI) or [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/).  
Copy this repo EFI folder to /Volumes/EFI/ so it will looks like this: 
>/Volumes/EFI/EFI/BOOT  
>/Volumes/EFI/EFI/OC  

Reboot.

## Specification
* Processor : Intel® Core™ i3-6006U 2.0 Ghz (Skylake)
* iGPU : Intel HD Graphics 520
* dGPU : Nvidia 920MX (Disabled)
* RAM : 4GB DDR4 2133MHz
* Built-in Audio : ALC255 Revision 2
* Ethernet : Realtek RTL8106E
* Keyboard : ATK PS/2
* Trackpad : ELAN1200 I2C
* Bootloader: OpenCore (UEFI)
* BIOS Version : X441UV.316

## What's worked
:white_check_mark:System Integrity Protection  
:white_check_mark:Quartz Extreme and Core Image (QE/CI) graphic acceleration   
:white_check_mark:Keyboard + Fn combination button (brightness button doesn't work [AsusSMC issue's](https://github.com/hieplpvip/AsusSMC/issues/75))  
:white_check_mark:Intel HD Graphics 520  
:white_check_mark:Ethernet  
:white_check_mark:USB ports 3.0/2.0 (manually mapped with [USBMap](https://github.com/corpnewt/USBMap), if some ports doesn't work consider using [USBInjectAll.kext](https://github.com/Sniki/OS-X-USB-Inject-All)  
:white_check_mark:Battery status    
:white_check_mark:Trackpad + Gesture  
:white_check_mark:Audio  
:white_check_mark:Backlight Control  
:white_check_mark:VGA port  
:white_check_mark:WebCam  
:white_check_mark:Shutdown / Reboot  
:white_check_mark:Sleep + Sleep on AC fix  
:white_check_mark: CPU temp  
:white_check_mark:GUI bootloader + boot chime  


## Not yet tested
FileVault  
HDMI Port

## Not worked
:x:DRM doesn't worked on [iGPU system](https://dortania.github.io/OpenCore-Post-Install/universal/drm.html).  
:x:dGPU : Nvidia 920MX (Disabled)  
:x:Card reader. I've tried [this](https://www.noobsplanet.com/index.php?threads/fix-internal-external-card-reader-hackintosh-guide.32/), but no luck.  
:x:Hibernate  
:x:Wifi. See notes.  

## Notes
* OpenCore 0.6.6
* Tested on Catalina 10.15.7. ==> still testing on BigSur
* This configuration include `AppleCpuPmCfgLock` and `AppleXcpmCfgLock` fix under Kernel -> Quirks which may cause instability in long term use. Please refer to [this guide](https://dortania.github.io/OpenCore-Post-Install/misc/msr-lock.html) for better permanent solution.
* I replaced my wifi card for dual band wireless support. Look at [this](https://osxlatitude.com/forums/topic/11138-inventory-of-supportedunsupported-wireless-cards-2-sierra-catalina/) for wifi fix. 
* USB 3.0/2.0 ports were manually mapped with [USBMap](https://github.com/corpnewt/USBMap), if some ports doesn't work consider using [USBInjectAll.kext](https://github.com/Sniki/OS-X-USB-Inject-All) or [remap](https://dortania.github.io/OpenCore-Post-Install/usb/#macos-and-the-15-port-limit) by yourself.
* Follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/update.html#updating-opencore) for updating OpenCore and kexts.

## Credits
[Apple](https://www.apple.com/) for MacOS.  
[acidanthera](https://github.com/acidanthera) for [OpenCore](https://github.com/acidanthera/OpenCorePkg) and kexts.  
[dortania](https://github.com/dortania) for [OpenCore Installation Guides](https://dortania.github.io/OpenCore-Install-Guide/)  
[hielplpvip](https://github.com/hieplpvip) for [AsusSMC kext](https://github.com/hieplpvip/AsusSMC)  
[Mieze](https://github.com/Mieze/) for [Realtek Ethernet kext](https://github.com/Mieze/RealtekRTL8100)  
[Sniki](https://github.com/Sniki/) for [USBInjectAll kext](https://github.com/Sniki/OS-X-USB-Inject-All/releases)  
[al3xtjames](https://github.com/al3xtjames) for [NoTouchID kext](https://github.com/al3xtjames/NoTouchID/)  
[corpnewt](https://github.com/corpnewt/) for [ProperTree](https://github.com/corpnewt/ProperTree), [USBMap tool](https://github.com/corpnewt/USBMap), [GenSMBIOS](
https://github.com/corpnewt/GenSMBIOS)  
[Olarila](https://www.olarila.com) for [Catalina vanilla image](https://www.olarila.com/topic/6278-new-vanilla-olarila-images/)  
[phantomhell](https://github.com/phantomhell) for [Asus X441UV Clover](https://github.com/phantomhell/Asus-X441UV-Hackintosh)  
[RehabMan](https://github.com/RehabMan/) for [VoodooPS2Controller](https://github.com/RehabMan/OS-X-Voodoo-PS2-Controller)
[alexandred](https://github.com/alexandred) for [VoodooI2C](https://github.com/VoodooI2C/VoodooI2C)  
