# iButton (USB-C)
External buttons for iOS devices, built on STM32 and USB HID middleware



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
