# PC Tool  
[Nuvoton tools official website](https://www.nuvoton.com/tool-and-software/software-development-tool/driver/)
## Development Tool
Debugger
- [KEIL Nu-Link debugger driver installer](https://www.nuvoton.com/resource-download.jsp?tp_GUID=SW1120200221180521)
- [IAR Nu-Link debugger driver installer](https://www.nuvoton.com/resource-download.jsp?tp_GUID=SW1120200221180914)
- [NuEclipse installer](https://www.nuvoton.com/resource-download.jsp?tp_GUID=SW1120200401182901)
- [PinView installer](https://www.nuvoton.com/resource-download.jsp?tp_GUID=SW1320200221181935)  
- [Customized pyOCD source code](https://github.com/OpenNuvoton/pyOCD) (using adapter firmware "NuLink2_DAPLink.bin")
- [Customized openOCD source code](https://github.com/OpenNuvoton/OpenOCD-Nuvoton)  (using adapter firmware "NuLink2FW.bin")
  
NuTool: Coding assistant  
- [PinConfig installer](https://www.nuvoton.com/resource-download.jsp?tp_GUID=SW1320200319135912)
- [ClockConfig installer](https://www.nuvoton.com/resource-download.jsp?tp_GUID=SW1320200930114649)

## Programmer Tool
- [ICPTool installer](https://www.nuvoton.com/resource-download.jsp?tp_GUID=SW1720200221181328)  
- [ISPTool installer](https://www.nuvoton.com/opencms/resource-download.jsp?tp_GUID=SW0320101221101703)  
- [ISPTool source code](https://github.com/OpenNuvoton/ISPTool)    
- [ISPTool command set](./doc/NuMicro_ISP_Flow_And_Command_Set.pdf)    
- [NuLink command tool installer](https://www.nuvoton.com/resource-download.jsp?tp_GUID=SW1720200221181644)  

<br>
<br>

# Nu-Link2-Pro debugging and programming adapter
When using debugging and programming tool above, you need an USB adapter. 
We introduce you a new feature-rich Nu-Link2-Pro adapter here.   
- [Where to buy](https://direct.nuvoton.com/tw/Nu-Link2-pro)   
- [User manual](https://www.nuvoton.com/resource-download.jsp?tp_GUID=UG1320200319174043)  
### The role of Nu-Link2-Pro adapter
User can switch roles that Nu-Link2-Pro play by re-programming Nu-Link2-Pro to another .bin file  
All Nu-Link2-Pro firmware image (.bin files) can be found [here](./Latest_NuLink_Firmware)  
#### How to update Nu-Link2-Pro firmware?
1. Press the button on Nu-Link2-Pro and plug in USB cable.
2. A "Nu-Link2-Pro" disk will show. (If you see disk name is "NuMicro MCU", it will upgrade DUT firmware instead of Nu-Link2-Pro itself) 
3. Drag and drop Nu-Link2-Pro image .bin into the disk.
4. Re-plug the USB cable and it's done.
#### More options for NuLink2FW
When you upgrade the NuLink2FW.bin version larger than v6131, and open NU.TXT in pop-up "NuMicro MCU" disk, you will see some options in NU.TXT .
For example, you can see Nu-Bridge and CMSIS-DAP option. 
Set Nu-Bridge=1 then re-plug in USB cable, Nu-Bridge function will be enabled. Nu-Bridge offers pass-through function for I2C/SPI/RS485/CAN interfaces. 
(You will see an additional "Nu-Bridge2 Virtual Com Port" in device manager.)
picture of NB2 (information about NB2)

Set Nu-Bridge=0 then re-plug in USB cable, ISP-Bridge function will be enabled. ISP-Bridge2 offers I2C/SPI/RS485/CAN interfaces those communicate with ISPTool.
(Note that Nu-Bridge and ISP-Bridge will not present at the same time.)

Set CMSIS-DAP=1 then re-plug in USB cable, it presents one more interface HID_CMSIS-DAP, this is handy if you want to use CMSIS-DAP protocol.

![](img/nulink2.PNG)

### Brief description of each adapter bin file  
#### [NuLink2FW.bin](./Latest_NuLink_Firmware)
- Proprietary code (except NuLink2FW.bin, most of Nu-Link2-Pro firmware are open source)
- Support NuMicro 8051, offline programming, user code read-out protection, unlimited flash break points, NuMicro chips specific features (config0/config1 dataflash setting, KPROM, etc.)
- USB interfaces: HID_ICE(proprietary commands)/MSC/VCOM/HID_CMSIS-DAP/HID_ISP or VCOM_NuBridge (set in NU.TXT)
- 


#### [NuLink2_ISP_Bridge.bin](./Latest_NuLink_Firmware)
- This is the latest image built from [NuLink2_ISP_Bridge](https://github.com/OpenNuvoton/NuLink2_ISP_Bridge)
- ISP bridge firmware is also integrated into NuLink2FW.bin (see HID_ISP above), so ISP tool can connect with NuLink2FW.bin, too.
- The target ISP loader code can be found at directory "BSP/SampleCode/ISP/" of each BSP. BSP can be found at https://github.com/OpenNuvoton or https://gitee.com/OpenNuvoton.  

#### [NuLink2_CMSIS_DAP.bin](./Latest_NuLink_Firmware)
- This is the latest image built from [CMSIS-DAP on Nu-Link2-Pro](https://github.com/OpenNuvoton/NuLink2_CMSIS_DAP)
- CMSIS-DAP firmware is also integrated into NuLink2FW.bin (see HID_CMSIS-DAP above).
- If you don't need rich features of DAPLink, this is the light weight choice of CMSIS-DAP firmware.


#### [NuLink2_DAPLink.bin](./Latest_NuLink_Firmware)
- This is the latest image built from [DAPLink on Nu-Link2-Pro](https://github.com/OpenNuvoton/DapLink)  
- Support many 3rd party IDE
- USB interfaces: HID(CMSIS-DAP commands)/MSC/VCOM 

#### [NuLink2_ISPLink2.bin](./Latest_NuLink_Firmware)
- This is the latest image built from [NuLink2_ISPLink2](https://github.com/OpenNuvoton/NuLink2_ISPLink2)
- The target ISP loader code can be found at directory "BSP/SampleCode/ISP/" of each BSP. BSP can be found at https://github.com/OpenNuvoton or https://gitee.com/OpenNuvoton.  

#### [NuLink2_ICP_Library.bin](./Latest_NuLink_Firmware)
- This is the latest image built from [ICP library](https://github.com/OpenNuvoton/NuLink2_ICP_Library)
- This sample code is useful when user wants to make his own programmer on another Cortex-M.
- ICPLib (two-wire ICP interface for NuMicro cortexM & 8051) on Nu-Link2 (M48SSIDAE)

https://github.com/OpenNuvoton/NuBridge2_script
https://github.com/OpenNuvoton/NuBridge2_Terminal
https://github.com/OpenNuvoton/NuBridge2_Firmware

<br>
<br>


