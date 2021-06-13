![OpenCore_with_text_Small](https://user-images.githubusercontent.com/74492520/121812516-a9290600-cc9a-11eb-8eae-436724334f58.png)
<h1 align="center">ASUS-TUF-GAMING-B460M-PLUS</h1>
<h3 align="center">华硕 B460M重炮手 黑苹果 OpenCore 引导配置</h3>
<br>

## Disclaimer / 免责声明

Your warranty is now void. Please do some research if you have any concerns before utilizing my project. I am not responsible for any loss, including but not limited to Kernel Panic, device fail to boot or can not function normally, storage damage or data loss, atomic bombing, World War III, The CK-Class Restructuring Scenario that SCP Foundation can not prevent, and so on.

你的保修将完全失效。如果您有任何疑虑，请在使用我的项目之前先进行一些研究。我对任何损失均不负责，包括但不限于 Kernel Panic、设备无法启动或无法正常工作、硬件损坏或数据丢失、原子弹爆炸、第三次世界大战、SCP 基金会无法避免的 CK 级现实重构等。

Please choose the branch you need for different graphics cards

不同显卡请选择你需要的分支


## Hardware Specifications / 硬件配置

| Specifications | Details |
|:---|:---|
| Computer Model | ASUS TUF GAMING B460M PLUS |
| CPU | Intel Core i3-10100 |
| Memory | DDR4 2666 Mhz. 8 GB |
| NVMe SSD | WD SN550 500G |
| Integrated Graphics | Intel UHD Graphics 630 |
| Wireless Card | NONE  |

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
| S3 Sleep / Hibernation Mode 3<br>S3 睡眠 / Mode 3 休眠 | ✅ | 


### Input & Output

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| USB 2.0, USB 3.0 | ✅ | `USBPorts.kext` | |

### Display, TrackPad and Keyboard / 显示器、触摸板和键盘

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| HiDPI | ✅ | | Natively enabled on UHD DP  screen external<br>在 UHD DP 4K 外接屏幕上原生启用 |

## Refrence / 必读参考资料

- [dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
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
- [MaciASL](https://github.com/acidanthera/MaciASL) for patching ACPI tables and editing ACPI patches.
  用于修补和编辑 ACPI 的工具 [MaciASL](https://github.com/acidanthera/MaciASL)
- [HackinTool](https://github.com/headkaze/Hackintool) for diagnosis ONLY. Most of the built-in patches are outdated.
  **仅用于** 诊断的 [HackinTool](https://github.com/headkaze/Hackintool)，大部分内置的补丁和工具已经过时、不再适用
- Patience and time, especially if this is your first time Hackintosh-ing.
  耐心和时间。如果你是第一次进行黑苹果，这尤为重要

### Hardware Modification / 硬件修改

#### SSD

Samusung PM981 is not supported AT ALL. Make sure to switch at least one SSD.

三星 PM981 **完全** 无法使用，务必更换至少一块 SSD 硬盘。


#### Wireless Card / 无线网卡

it is recommended to use Broadcom wireless network card for the best experience (better, refer to the use of the best experience).

建议使用博通无线网卡以获得 **更好** 的体验（更好，指使用 **体验**）。


### BIOS Settings / 修改 BIOS 设置

- Settings > Advanced > System Agent (SA) Configuration > VT-D: Disabled
- Settings > Advanced > System Agent (SA) Configuration > Above 4G Decoding: Enabled
- Settings > Advanced > USB Configuration > XHCI Hand-off: Enabled
- Settings > Boot > CSM(Compatibility Support Module) > Launch CSM: Disabled
- Settings > Boot > Secure Boot > OS Type: Other OS
- Settings > Boot > Boot\Boot Configuration > Wait For 'F1' If Error: Disabled



## Donation / 捐赠

Donating to this project is OPTIONAL. But feel free to buy me a coffee if you appreciate my works.

捐赠本项目 **并不是必需的**。但是如果我的项目对你有所帮助，为什么不考虑一下给我买杯咖啡呢？
![C7EF578BCA72E3AC13BCC464E0F42B95](https://user-images.githubusercontent.com/74492520/121812676-61ef4500-cc9b-11eb-8c67-95bc62d45523.png)
![E3EC06A7B64C92117AAC545F9B08F343](https://user-images.githubusercontent.com/74492520/121812678-63b90880-cc9b-11eb-9650-4f85fb2770c6.jpg)
