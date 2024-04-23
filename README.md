# iButton (USB-C)
 [English](README_EN.md)

为配备 USB Type-C 接口的 iOS 设备提供外置的物理按键，可自定义功能。

由 STM32 上的 USB HID middleware 实现，模拟了外置鼠标上的自定义按键。

按键功能在`辅助功能` - `触控` - `辅助触控` 中设置。



![Design Preview](assets/preview.jpg)



## 构建环境

- 主控固件管理和代码生成: **STM32CubeMX**
- 代码编辑器/开发工具: **CLion**
- 编译器: **gcc-arm-none-eabi**
- 烧录工具: **ST-Link Utility** or **STM32CubeProgrammer** or **OpenOCD**

注意：使用 STM32CubeMX 时，可能会要求登录 ST account 。



## 项目文件

- [iButton-FW](iButton-FW1/): 主要固件代码 (CLion/CubeIDE)
- [STM32-iButton](STM32-iButton-v3/): 主板 (立创EDA Pro)
- [EdgeLink](EdgeLink2/): ST-Link V2 to EdgeLink 转接器 (KiCAD)
- [EdgDbg](EdgDbg3/): ST-Link 带有 EdgeLink 连接器 (立创EDA Pro)
- [Case3D](Case3D/): 3D 外壳模型 (Shapr3D)
- [Datasheet](Datasheet/): 参考资料 (PDF)

其中 EdgDbg（Edge-Debugger）的基底是 [开源 ST-Link-V2](https://oshwhub.com/CYIIOT/ST_LINK-V2_1)，将 SWD 相关接口改成 EdgeLink 而成。



## Notes

BOOT0默认下拉到GND；要使STM32启动到下载模式，需要将BOOT0置高。在EdgeLink金手指连接器处，BOOT0直接连接VCC，这样当板卡插入EdgeLink调试器时就会进入下载模式。VCC可选5V或3V3，STM32微控制器的BOOT0是否接受5V输入需要视型号而定。对于STM32L052系列，BOOT0最大输入为VDD+4V，因此可以安全连接。

要烧录和调试STM32-iButton-v3主板，需要使用EdgDbg硬件或EdgeLink+ST-Link（它们是等价的）。
