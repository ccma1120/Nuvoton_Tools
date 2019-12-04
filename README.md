# Development Tool
[Nu-Link driver and NuTool](https://www.nuvoton.com/hq/support/tool-and-software/software/development-tool/)
# Programmer
[ICPTool and ISPTool](https://www.nuvoton.com/hq/support/tool-and-software/software/programmer/)
# Nu-Link2 debugging and programming adapter
The role of Nu-Link2 adapter 
#![img](img\nulink2.JPG)


NuLink2FW.bin
Proprietary code vs. open source
Both have HID/MSC/VCOM (Nu-Link1 need jumper)
HID (proprietary command vs. CMSIS-DAP)
Nu-Link2 proprietary FW 
(Support NuMicro 8051, NuMicro specific features (config0/config1 dataflash setting, KPROM, etc.), unlimited flash break points, offline programming, user code protection) 
DAPLink on Nu-Link2 (3rd party IDE, customized ICE, mbed compatible, …)
FW upgrade: Consider using switch, switch between (DAPLink and NuLink2)

NuLink2_DAPLink.bin

# Nu-Link2 open platform
## Open source firmware
[DAPLink on Nu-Link2](https://github.com/OpenNuvoton/DapLink)   
[ISP bridge](https://github.com/OpenNuvoton/NuLink2_ISP_Bridge)    
[ICP library](https://github.com/OpenNuvoton/NuLink2_ICP_Library)
## On chip debugging
[pyOCD for Nu-Link2 (using CMSIS-DAP)](https://github.com/OpenNuvoton/pyOCD)


I2P bridge FW on Nu-Link2 only
Standalone <open-source> 
Integrate with ICE


ISP-Link2 FW on Nu-Link2
Standalone <open-source> 
Program ISPLink2 FW to Nu-Link2 -> pop up a USB DISK -> format it
Put DEFINE.TXT, TEST1.BIN into DISK
DEFINE.TXT
START
APROM=1
0:\\test1.bin
DATAFLASH=0
0:\\test2.bin
END

Bus Monitor tool

I2C (PIN 3, 4)，SPI (PIN 5~8 – SS, CLK, MOSI, MISO)，RS485 (PIN 9, 10)，CAN (PIN 11, 12)，GND (PIN 18, 20)

configuration
目前沒有開任何選項，都是固定寫死。
SPI Bus 的傳輸只能是 Mode 0，Bit Length 8
RS485 Bus 的 Baud Rate 是 115200
CAN Bus 的 Baud Rate 是 500K


Data Only HEX (00-FF)
註：底層仍是 RS232

CAN 支援兩種格式的 ID
STD (11 bit ID HEX, 0~7FF)
EXT (29 bit ID HEX)
DLC 是 Data 長度
DATA, HEX (0000 - FFFF)


CAN/485/I2C/SPI Monitor tool FW (NuLink2 only)
Standalone: Bandwidth requirement



Nu-Link ICP Library

ICPLib (two-wire ICP interface for NuMicro cortexM & 8051)
Nu-Link1 (NUC12SRE3DN)
Nu-Link2 (M48SKIDAE)



