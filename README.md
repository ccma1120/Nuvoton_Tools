# PC Tool [Official webpage](https://www.nuvoton.com/hq/support/tool-and-software/development-tool-hardware/)
## Development Tool
Debugger
- [KEIL Nu-Link debugger driver installer](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW0520101208200142)
- [IAR Nu-Link debugger driver installer](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW0520101208200227)
- [NuEclipse installer](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW1020180913190214)
- [pyOCD (debug adapter with CMSIS-DAP commands)](../../../pyOCD)
- [openOCD (debug adapter with Nu-Link proprietary commands)](../../../Nuvoton-OpenOCD)
- [PinView](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW1020160317155513)  

NuTool: Coding assistant  
- [PinConfig](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW1020150724174251)
- [ClockConfig](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW1020161014155032)
- CodeGen (coming soon)

## Programmer Tool
- [ICPTool installer](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW0520101208200310)  
- [ISPTool installer](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW0320101221101703)  
- [ISPTool source code](../../../ISPTool/)    
- [NuLink command tool installer](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW0520160317094731)  
  
# Nu-Link2 debugging and programming adapter
When using debugger and programmer tool above, you need an USB apatper. 
We introduce you a new feature-rich Nu-Link2 adapter here.
## The role of Nu-Link2 adapter
![](img/nulink2.PNG)

All Nu-Link2 firmware image (.bin files) can be found [here](./Latest_NuLink_Firmware)

### NuLink2FW.bin
- Proprietary code (most of Nu-Link2 firmware are open source except NuLink2FW.bin)
- USB interfaces HID(proprietary commands)/MSC/VCOM 
- Support NuMicro 8051, NuMicro specific features (config0/config1 dataflash setting, KPROM, etc.), unlimited flash break points, offline programming, user code protection

### NuLink2_DAPLink.bin
- This is the latest image built from [DAPLink on Nu-Link2](https://github.com/OpenNuvoton/DapLink)
- USB interfaces HID(CMSIS-DAP)/MSC/VCOM 
- Support many 3rd party IDE

### NuLink2_CMSIS_DAP.bin
- This is the latest image built from [CMSIS-DAP on Nu-Link2](https://github.com/OpenNuvoton/NuLink2_CMSIS_DAP)
- If you don't need rich features of DAPLink, this is the light weight choice of CMSIS-DAP firmware.

### NuLink2_ISP_Bridge_FW.bin
- This is the latest image built from [NuLink2_ISP_Bridge](https://github.com/OpenNuvoton/NuLink2_ISP_Bridge)
- ISP bridge firmware is also integrated into NuLink2FW.bin, so ISP tool can connect with NuLink2FW.bin, too.

### NuLink2_ISPLink2.bin
- This is the latest image built from [NuLink2_ISPLink2](https://github.com/OpenNuvoton/NuLink2_ISPLink2)
- Program ISPLink2 FW to Nu-Link2 -> pop up a USB DISK -> format it
Put DEFINE.TXT, TEST1.BIN into DISK
DEFINE.TXT
START
APROM=1
0:\\test1.bin
DATAFLASH=0
0:\\test2.bin
END

### NuLink2_ICP_Library.bin
- This is the latest image built from [ICP library](https://github.com/OpenNuvoton/NuLink2_ICP_Library)
- ICPLib (two-wire ICP interface for NuMicro cortexM & 8051)
Nu-Link1 (NUC12SRE3DN)
Nu-Link2 (M48SKIDAE)

### NuLink2_Bus_Monitor.bin
![](img/bus_monitor_wsg.png)



## How to update Nu-Link2 firmware?
1. Press the button on Nu-Link2 and plug in USB cable.
2. A "Nu-Link2" disk will show. (If you see disk name is "NuMicro MCU", it will upgrade DUT firmware instead of Nu-Link2 itself) 
3. Drag and drop Nu-Link2 image .bin into the disk.
4. Re-plug the USB cable and it's done.

