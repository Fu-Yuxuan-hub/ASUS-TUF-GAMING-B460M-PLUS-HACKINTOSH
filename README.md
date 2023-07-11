ASUS TUF GAMING B460M PLUS
========
EFI for ASUS TUF GAMING B460M PLUS

English(current)<br>
[简体中文](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/blob/main/README_CN.md)


## Disclaimer 

Your warranty is now void. Please do some research if you have any concerns before utilizing my project. I am not responsible for any loss, including but not limited to Kernel Panic, device fail to boot or can not function normally, storage damage or data loss, atomic bombing, World War III, The CK-Class Restructuring Scenario that SCP Foundation can not prevent, and so on.


## Practical Manual 
- [English](https://dlsvr04.asus.com.cn/pub/ASUS/mb/LGA1200/TUF_GAMING_B460M-PLUS/E17227_TUF_GAMING_B460M-PLUS_UM_V3_WEB.pdf)

## Hardware Specifications 

| Specifications | Details |
|:---|:---|
| Computer Model | ASUS TUF GAMING B460M PLUS |
| CPU | Intel Core i3-10100 |
| Memory | DDR4 2666 Mhz. 8 GB |
| NVMe SSD | WD SN550 500G |
| Integrated Graphics | Intel UHD Graphics 630 |
| Wireless Card | BCM 943602CS |
| [BIOS Version](https://www.asus.com.cn/motherboards-components/motherboards/tuf-gaming/tuf-gaming-b460m-plus/helpdesk_bios/?model2Name=TUF-GAMING-B460M-PLUS) | Version 1301 |

## Working & Not Working 

### Non-Fuctional 

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| Wi-Fi | ❌ | *IO80211FamilyLegacy* | Apple has removed this kext in *macOS Sonoma* |


### Video and Audio

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| Full Graphics Accleration (QE/CI) | ✅ | *WhateverGreen.kext* | |
| Audio Recording via 3.5mm microphone | ✅ | *AppleALC.kext* | |
| Audio Playback after through 3.5mm | ✅ | *AppleALC.kext* | |
| Automatic Headphone Output Switching | ✅ | *AppleALC.kext* | |


### Power, Charge, Sleep and Hibernation 

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| CPU Power Management (SpeedShift) | ✅ | *SSDT-PLUG* | Use *iMac20,1* |
| NVMe Drive Battery Management | ✅ | | |
| S3 Sleep | ✅ |
| Hibernate Mode 25 | ✅ | 1. Enter *sudo pmset hibernatemode 25* in the terminal<br>2. *Booter-DiscardHibernateMap* *enable*<br>3. *Misc-Boot-Hibernate Mode* *Auto*<br>4. Third-party SSD enable *Kernel-Quirks-ThirdPartyDrivers*
  | |

### Input & Output

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| USB 2.0, USB 3.0 | ✅ | *USBPorts.kext* | It is recommended to ***re-customize*** the USB |


### Display, TrackPad and Keyboard 

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| HiDPI | ✅ | | Natively enabled on UHD DP  screen external |


## Refrence 

- [dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [dortania's OpenCore Post Install Guide](https://dortania.github.io/OpenCore-Post-Install/)
- [dortania Getting Started with ACPI](https://dortania.github.io/OpenCore-Post-Install/)
- *Configuration.pdf* and *Differences.pdf* in each OpenCore releases.
- [daliansky/OC-little](https://github.com/daliansky/OC-little)
- [OpenCore 简体中文参考手册 (非官方)](https://oc.skk.moe)

**No seriously, PLEASE read those.**

## Requirement 

### Basic 

- Flash drive, 4GB or more, for the above purpose.

- [OCAuxiliaryTools](https://github.com/ic005k/OCAuxiliaryTools) to edit plist files on Windows/macOS.

- [ProperTree](https://github.com/corpnewt/ProperTree) to edit plist files on Windows/macOS.

- [MaciASL](https://github.com/acidanthera/MaciASL) for patching ACPI tables and editing ACPI patches.

- [HackinTool](https://github.com/headkaze/Hackintool) for diagnosis ONLY. Most of the built-in patches are outdated.

- Patience and time, especially if this is your first time Hackintosh-ing.


### Hardware Modification 

#### SSD

Samusung PM981/PM981a/PM991 and Micron 2200S is not supported AT ALL. Make sure to switch at least one SSD.


#### Wireless Card

- It is recommended to use Broadcom wireless network card to obtain **Better** performance and use native functions about「Apple Ecology」
  >In macOS Sonoma ，Apple has removed *IO80211FamilyLegacy* which made the Broadcom wireless card no longer available in macOS Sonoma.


### BIOS Settings 

- Settings > Advanced > System Agent (SA) Configuration > VT-D: Disabled
- Settings > Advanced > System Agent (SA) Configuration > Above 4G Decoding: Enabled
- Settings > Advanced > USB Configuration > XHCI Hand-off: Enabled
- Settings > Boot > CSM(Compatibility Support Module) > Launch CSM: Disabled
- Settings > Boot > Secure Boot > OS Type: Other OS
- Settings > Boot > Boot\Boot Configuration > Wait For 'F1' If Error: Disabled


### Solve the Windows difference of 8 hours 
* Running under the Window 
```
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```

## Contribution

#### If you like this project, please consider supporting it via:

* Give it a star!

* [Buy](https://ko-fi.com/fuyuxuan) me a coffee😝.
  * Also can [WeChat](https://github.com/Fu-Yuxuan-hub/Generic-EFI-for-H610-B660-Z690-B760-Z790/blob/main/Donation/WeChat.JPG) or [Alipay](https://github.com/Fu-Yuxuan-hub/Generic-EFI-for-H610-B660-Z690-B760-Z790/blob/main/Donation/Alipay.JPG)

* Opening up an issue if you encountered any problem or want to make suggestions.
  > Attention：Please ask questions according to the predetermined template

## Credits

* [acidanthera](https://github.com/acidanthera) for OpenCore.
* Apple for macOS.

## Attention

* This repo is only for sharing and helping install Hackintosh, **not for** commercial use.

© 杆杆只爱学习, Released under the MIT License.