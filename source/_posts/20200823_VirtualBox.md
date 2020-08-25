---
title: VirtualBox虚拟机无法识别网银U盾的解决方案
tags: vm
---

## Situation
主机: macOS Ver. 10.15.6
虚拟机: VirtualBox Ver. 6.1.12 + Windows 10

* 在主机上插入招商银行23版UKey, 在Win VM中可以看到一个 USB TOKEN设备. 但是挂载时提示错误.
* 在VBox settings -> Ports -> USB -> USB Device Filters中尝试加载新设备时, 得到的是Vendor ID与Product ID均为0000的unknown device.

## 解决方案
1. 确认VBox已安装Oracle VM VirtualBox Extension Pack
2. 在主机上插入UKey
3. 访问 About This Mac -> System Report -> Hardware / USB, 找到名为Token的设备
    * 记录Vendor ID与Product ID
4. 在VBox settings中, 修改USB device filter, 填入
    * Name = Token
    * Vendor ID 
    * Product ID
5. 拔出UKey
6. 启动Win VM
7. 插入UKey
