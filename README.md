<h1 align="center">ASUS-TUF-GAMING-B460M-PLUS</h1>
<h3 align="center">华硕 B460M重炮手 黑苹果 OpenCore 引导配置</h3>
<br>

## Disclaimer / 免责声明

Your warranty is now void. Please do some research if you have any concerns before utilizing my project. I am not responsible for any loss, including but not limited to Kernel Panic, device fail to boot or can not function normally, storage damage or data loss, atomic bombing, World War III, The CK-Class Restructuring Scenario that SCP Foundation can not prevent, and so on.

你的保修将完全失效。如果您有任何疑虑，请在使用我的项目之前先进行一些研究。我对任何损失均不负责，包括但不限于 Kernel Panic、设备无法启动或无法正常工作、硬件损坏或数据丢失、原子弹爆炸、第三次世界大战、SCP 基金会无法避免的 CK 级现实重构等。


## ASUS-TUF-GAMING-B460M-PLUS  Practical Manual / 使用手册 
- [English](https://dlsvr04.asus.com.cn/pub/ASUS/mb/LGA1200/TUF_GAMING_B460M-PLUS/E17227_TUF_GAMING_B460M-PLUS_UM_V3_WEB.pdf)

- [简体中文](https://dlsvr04.asus.com.cn/pub/ASUS/mb/LGA1200/TUF_GAMING_B460M-PLUS/C17227_TUF_GAMING_B460M-PLUS_UM_V3_WEB.pdf)

  ## 

## Hardware Specifications / 硬件配置

| Specifications | Details |
|:---|:---|
| Computer Model | ASUS TUF GAMING B460M PLUS |
| CPU | Intel Core i3-10100 |
| Memory | DDR4 2666 Mhz. 8 GB |
| NVMe SSD | WD SN550 500G |
| Integrated Graphics | Intel UHD Graphics 630 |
| Wireless Card | BCM 943602CS |

## Working & Not Working / 可用与不可用的功能

### Non-Fuctional / 不工作

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| Non-Fuctional<br>没有不工作 | ✅ |  | Completely normal<br>完全正常 |


### Video and Audio / 音频与视频

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| Full Graphics Accleration (QE/CI)<br>图形硬件加速 | ✅ | `WhateverGreen.kext` | |
| Audio Recording via 3.5mm microphone<br>通过3.5mm 麦克风录音 | ✅ | `AppleALC.kext` | |
| Audio Playback after through 3.5mm<br>通过 后 3.5mm 接口播放音频 | ✅ | `AppleALC.kext` | |
| Automatic Headphone Output Switching<br>当插入耳机时自动切换音频输出 | ✅ | `AppleALC.kext` | |


### Power, Charge, Sleep and Hibernation / 电源管理、充电、睡眠、休眠

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| CPU Power Management (SpeedShift)<br>CPU 电源管理 | ✅ | `SSDT-PLUG` | Use `iMac20,1` |
| NVMe Drive Battery Management<br>NVMe 硬盘电源管理 | ✅ | `NVMeFix.kext` | |
| S3 Sleep<br>S3 睡眠 | ✅ | 
| Hibernation Mode 3<br>Mode 3 休眠 | ✅ |   | `may broken`<br>`可能无法使用` |

### Input & Output

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| USB 2.0, USB 3.0 | ✅ | `USBPorts.kext` | 建议自行`重新定制`USB |


### Display, TrackPad and Keyboard / 显示器、触摸板和键盘

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| HiDPI | ✅ | | Natively enabled on UHD DP  screen external<br>在 UHD DP 4K 外接屏幕上原生启用 |

## Refrence / 必读参考资料

- [dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [dortania's OpenCore Post Install Guide](https://dortania.github.io/OpenCore-Post-Install/)
- [dortania Getting Started with ACPI](https://dortania.github.io/OpenCore-Post-Install/)
- [dortania opencore multiboot](https://github.com/dortania/OpenCore-Multiboot)
- [WhateverGreen Intel HD Manual](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.IntelHD.en.md)
- `Configuration.pdf` and `Differences.pdf` in each OpenCore releases.
- [daliansky/OC-little](https://github.com/daliansky/OC-little)
- [OpenCore 简体中文参考手册 (非官方)](https://oc.skk.moe)

**No seriously, PLEASE read those.**

**务必阅读上述参考资料**

## Requirement / 需求和依赖

### Basic / 基本需求

- A macOS machine (optional): to create the macOS installer and build the EFI.
  一台已经安装好 macOS 的机器，用于制作 macOS 安装器和编译本项目
- Flash drive, 16GB or more, for the above purpose.
  一个容量大于等于 16 GiB 的 U 盘
- [PlistEDPlus](https://github.com/ic005k/PlistEDPlus) to edit plist files on Windows.
  编辑 plist 文件的工具 [PlistEDPlus](https://github.com/ic005k/PlistEDPlus)
- [ProperTree](https://github.com/corpnewt/ProperTree) to edit plist files on Windows/macOS.
  编辑 plist 文件的工具 [ProperTree](https://github.com/corpnewt/ProperTree)
- [MaciASL](https://github.com/acidanthera/MaciASL) for patching ACPI tables and editing ACPI patches.
  用于修补和编辑 ACPI 的工具 [MaciASL](https://github.com/acidanthera/MaciASL)
- [HackinTool](https://github.com/headkaze/Hackintool) for diagnosis ONLY. Most of the built-in patches are outdated.
  **仅用于** 诊断的 [HackinTool](https://github.com/headkaze/Hackintool)，大部分内置的补丁和工具已经过时、不再适用
- Patience and time, especially if this is your first time Hackintosh-ing.
  耐心和时间。如果你是第一次进行黑苹果，这尤为重要

### Hardware Modification / 硬件修改

#### SSD

三星 PM981/PM981a/PM991 和 镁光 2200S **完全** 无法使用，务必更换至少一块 SSD 硬盘。

Samusung PM981/PM981a/PM991 and Micron 2200S is not supported AT ALL. Make sure to switch at least one SSD.


#### Wireless Card / 无线网卡

It is recommended to use Broadcom wireless network card to obtain **Better** performance and use native functions about「Apple Ecology」(I mean, 100x FASTER!)

建议使用博通无线网卡以获得 **更好** 的性能和使用原生的关于「苹果生态」的功能（更好，指速度快 **100 倍**）


### BIOS Settings / 修改 BIOS 设置

- Settings > Advanced > System Agent (SA) Configuration > VT-D: Disabled
- Settings > Advanced > System Agent (SA) Configuration > Above 4G Decoding: Enabled
- Settings > Advanced > USB Configuration > XHCI Hand-off: Enabled
- Settings > Boot > CSM(Compatibility Support Module) > Launch CSM: Disabled
- Settings > Boot > Secure Boot > OS Type: Other OS
- Settings > Boot > Boot\Boot Configuration > Wait For 'F1' If Error: Disabled


### Solve the windows difference of 8 hours / 双系统解决Win系统时间时差问题
* Running under the Window / 在Windows下运行
```
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```

## End / 结语
This EFI supports `macOS Catalina`,`macOS Big Sur`,`macOS Monterey` and `macOS Ventura Beta`       

本项目所提供的EFI支持`macOS Catalina`,`macOS Big Sur`,`macOS Monterey`和`macOS Ventura Beta`


Welcome to submit [Issue](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/issues) and [Pull request](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/pulls)

欢迎各位积极提交[Issue](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/issues)和[Pull request](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/pulls)
