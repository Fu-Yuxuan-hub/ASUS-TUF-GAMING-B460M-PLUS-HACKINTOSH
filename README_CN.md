ASUS TUF GAMING B460M PLUS
========
提供给 ***ASUS TUF GAMING B460M PLUS*** 主板使用的 EFI

[English](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/blob/main/README.md)<br>
简体中文(当前)


## 免责声明

你的保修将完全失效。如果您有任何疑虑，请在使用我的项目之前先进行一些研究。我对任何损失均不负责，包括但不限于 Kernel Panic、设备无法启动或无法正常工作、硬件损坏或数据丢失、原子弹爆炸、第三次世界大战、SCP 基金会无法避免的 CK 级现实重构等。


## 使用手册 

- [简体中文](https://dlsvr04.asus.com.cn/pub/ASUS/mb/LGA1200/TUF_GAMING_B460M-PLUS/C17227_TUF_GAMING_B460M-PLUS_UM_V3_WEB.pdf)


##  硬件配置

| Specifications | Details |
|:---|:---|
| Computer Model | ASUS TUF GAMING B460M PLUS |
| CPU | Intel Core i3-10100 |
| Memory | DDR4 2666 Mhz. 8 GB |
| NVMe SSD | WD SN550 500G |
| Integrated Graphics | Intel UHD Graphics 630 |
| Wireless Card | BCM 943602CS |
| [BIOS Version](https://www.asus.com.cn/motherboards-components/motherboards/tuf-gaming/tuf-gaming-b460m-plus/helpdesk_bios/?model2Name=TUF-GAMING-B460M-PLUS) | Version 1301 |

##  可用与不可用的功能

###  不工作

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| Wi-Fi | ❌ | *IO80211FamilyLegacy* | *macOS Sonoma* 中需要 [OCLP](https://github.com/dortania/OpenCore-Legacy-Patcher/pull/1077) |


### 音频与视频

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| 图形硬件加速 | ✅ | *WhateverGreen.kext* | |
| 通过3.5mm 麦克风录音 | ✅ | *AppleALC.kext* | |
| 通过 后 3.5mm 接口播放音频 | ✅ | *AppleALC.kext* | |
| 当插入耳机时自动切换音频输出 | ✅ | *AppleALC.kext* | |


### 电源管理、充电、睡眠、休眠

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| CPU 电源管理 | ✅ | *SSDT-PLUG* | Use *iMac20,1* |
| NVMe 硬盘电源管理 | ✅ | | |
| S3 Sleep | ✅ | 
| Hibernate Mode 25 | ✅ | 1. 终端输入 *sudo pmset hibernatemode 25*<br>2. *Booter-DiscardHibernateMap* *启用*<br>3. *Misc-Boot-Hibernate Mode* *Auto*<br>4. 第三方 SSD 启用 *Kernel-Quirks-ThirdPartyDrivers*
 | |

### 输入 & 输出

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| USB 2.0, USB 3.0 | ✅ | *USBPorts.kext* | 建议自行 ***重新定制*** USB |


### 显示器、触摸板和键盘

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| HiDPI | ✅ | | 在 UHD DP 4K 外接屏幕上原生启用 |


## 必读参考资料

- [dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [dortania's OpenCore Post Install Guide](https://dortania.github.io/OpenCore-Post-Install/)
- [dortania Getting Started with ACPI](https://dortania.github.io/OpenCore-Post-Install/)
- *Configuration.pdf* and *Differences.pdf* in each OpenCore releases.
- [daliansky/OC-little](https://github.com/daliansky/OC-little)
- [OpenCore 简体中文参考手册 (非官方)](https://oc.skk.moe)

**务必阅读上述参考资料**

## 需求和依赖

### 基本需求

- 一个容量大于等于 4 GB 的 U 盘

- 编辑 plist 文件的工具 [OCAuxiliaryTools](https://github.com/ic005k/OCAuxiliaryTools)

- 编辑 plist 文件的工具 [ProperTree](https://github.com/corpnewt/ProperTree)

- 用于修补和编辑 ACPI 的工具 [MaciASL](https://github.com/acidanthera/MaciASL)

- **仅用于** 诊断的 [Hackintool](https://github.com/headkaze/Hackintool)，大部分内置的补丁和工具已经过时、不再适用

- 耐心和时间。如果你是第一次进行黑苹果，这尤为重要

### 硬件修改

#### SSD

三星 PM981/PM981a/PM991 和 镁光 2200S **完全** 无法使用，务必更换至少一块 SSD 硬盘。

#### Wireless Card / 无线网卡

- 建议使用博通无线网卡以获得 **更好** 的性能和使用原生的关于「苹果生态」的功能
  >在 macOS Sonoma 中，Apple 已经删除了 *IO80211FamilyLegacy*，这导致博通无线网卡在 macOS Sonoma 中需要使用 [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher/pull/1077) 驱动。


### BIOS Settings / 修改 BIOS 设置

- Settings > Advanced > System Agent (SA) Configuration > VT-D: Disabled
- Settings > Advanced > System Agent (SA) Configuration > Above 4G Decoding: Enabled
- Settings > Advanced > USB Configuration > XHCI Hand-off: Enabled
- Settings > Boot > CSM(Compatibility Support Module) > Launch CSM: Disabled
- Settings > Boot > Secure Boot > OS Type: Other OS
- Settings > Boot > Boot\Boot Configuration > Wait For 'F1' If Error: Disabled


### Windows 系统时间时差
* 在 Windows 下运行
```
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```

## 贡献 / Contribution

#### 如果您喜欢这个项目，请考虑通过以下方式支持它：

* 给它一颗星！

* 给我[买](https://ko-fi.com/fuyuxuan)一杯咖啡😝。
  * 也可以通过 [微信](https://github.com/Fu-Yuxuan-hub/Generic-EFI-for-H610-B660-Z690-B760-Z790/blob/main/Donation/WeChat.JPG) 或 [支付宝](https://github.com/Fu-Yuxuan-hub/Generic-EFI-for-H610-B660-Z690-B760-Z790/blob/main/Donation/Alipay.JPG)

* 如果您遇到任何问题或想提出建议，请提出issue。
  > 注意：请按照预定的模版提问

## Credits

* [acidanthera](https://github.com/acidanthera) for OpenCore.
* Apple for macOS.

## 注意

* 此仓库仅用于分享和帮助安装 Hackintosh，**请勿** 用于商业用途。

© 杆杆只爱学习, Released under the MIT License.