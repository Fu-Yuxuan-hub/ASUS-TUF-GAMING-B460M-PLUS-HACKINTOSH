## OpenCore 0.8.8

Happy New Year! -May the New Year bring many good things and rich blessings to you and all those you love!
This is the first release in 2023, and the following is changlog.

- Update OpenCore to 0.8.8
- Set `LauncherOption` to `Full`
- Add `shikigva=80/128` to Fix [DRM](https://dortania.github.io/OpenCore-Post-Install/universal/drm.html#fixing-drm) for dGPU -Refer to [DRM Compatibility Chart for 10.15](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.Chart.md)
- Add `#USBPorts.kext` with all ports
- Add some `config.plist` for different GPU (Please choose the right config.plist)
- Simplify `ApplcALC.kext`
- Here is the [Network Interface Card Driver](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/issues/4)
- Please generate the new SMBIOS
- If you use [USBToolBox](https://github.com/USBToolBox/tool) to map your USB, you should unload `XHCI-unsupported.kext`
- If you want to use dual displays with iGPU, please send an email to Fu-Yuxuan@outlook.com
- If you have any problem,please [sumit new issue](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/issues)

The next version will be release in Jun./Jul. 2023 (**maybe** -When the next macOS fireware is published)
As an aside, the EFI version doesn't mean it works well. **A stable EFI is essential**, so don't blindly pursue new versions. Just like me, I **only** updated the EFI once last year(When the macOS Ventura was published)


新年快乐！ -辞暮尔尔 烟火年年 朝朝暮暮 岁岁平安
这是2023年的首个正式版，以下为更新日志
- 升级OpenCore至0.8.8
- 将`LauncherOption` 设置为 `Full`
- 增加`shikigva=80/128`以修复独显[DRM](https://dortania.github.io/OpenCore-Post-Install/universal/drm.html#fixing-drm) -参考[DRM Compatibility Chart for 10.15](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.Chart.md)
- 增加全端口的`#USBPorts.kext`
- 为不同的显卡增加了新的`config.plist`
- 精简`ApplcALC.kext`
- 这里是[无线网卡驱动](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/issues/4)
- 请生成新的三码
- 如果你使用[USBToolBox](https://github.com/USBToolBox/tool)定制你的USB，请取消加载`XHCI-unsupported.kext`
- 如果你想用核显输出双显示器，请发邮件至Fu-Yuxuan@outlook.com
- 如果你有任何问题，请创建一个[新的issue](https://github.com/Fu-Yuxuan-hub/ASUS-TUF-GAMING-B460M-PLUS-HACKINTOSH/issues)

下一个版本我可能会于2023年6/7月更新（**可能** -当下一个macOS固件推出时）
说点题外话，EFI版本不代表它能稳定工作，**一个稳定的EFI是重要的**，所以不要盲目去追求新的版本。就像我一样，去年我**仅仅**更新了一次EFI（当macOS Ventura被推出时）