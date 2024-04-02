# iButton (USB-C)
External buttons for iOS devices, built on STM32 and USB HID middleware.

The buttons can be configured in Accessibility to control the iOS device. It acts as an external mouse with user configurable keys.



## Build Environment

- Firmware Manager: **STM32CubeMX**
- Code Editor / IDE: **CLion**
- Compiler: **gcc-arm-none-eabi**
- Imager: **ST-Link Utility** or **STM32CubeProgrammer** or **OpenOCD**

To download some necessary packages in STM32CubeMX, you will need an ST account.



## Project Structure

- iButton-FW: Main firmware code (CLion/CubeIDE)
- STM32-iButton: Main circuit board (KiCAD)
- EdgeLink: ST-Link V2 to EdgeLink Adaptor (KiCAD)
- EdgDbg: ST-Link with EdgeLink connector (LCEDA Pro)
- Case3D: 3D case (Shapr3D)
- Datasheet: references (PDF)



## Notes

BOOT0默认下拉到GND；要使STM32启动到下载模式，需要将BOOT0置高。在EdgeLink金手指连接器处，BOOT0直接连接VCC，这样当板卡插入EdgeLink调试器时就会进入下载模式。VCC可选5V或3V3，STM32微控制器的BOOT0是否接受5V输入需要视型号而定。对于STM32L052系列，BOOT0最大输入为VDD+4V，因此可以安全连接。
