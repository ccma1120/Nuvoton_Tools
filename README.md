
```mermaid
gantt
dateFormat  YYYY-MM
title MS60 plan

section ms00
ms70 man power for nucodegen      : 2020-06,2020-09

section ycc
m030g/m0a21 offline             :   done, a1, 2020-04,1d
m471 (one more dataflash, xom, bank swap, otp) modify tool              :  done, a2, after a1, 30d
m2354 MP, tc8250 get board dpm nulink2            :  a3, after a1, 30d
ml56/ m0a21 nulink2 after get board:   
m031 + m030g/m0a21  modify tool : a4, after a3, 20d
multi debugger for NUA3500, ICPLib M030G               :         a5, after a4, 45d

section cctu
NuSenadj       : b1, 2020-04, 15d
NuBridge2 basic+script             :done, b2, after b1,15d
NuBridge2 log, UM: b3, after b2  , 15d
isp bridge ap note  :b4, after b3 , 16d 
ISP cross platform, command line: b5, after b4 , 50d 
(stm32cube monitor) ADC/PWM/SWD chart  :  

section cyyu
rtt pin            : done, c1, 2020-04,1d
rtt clock: done, c2, after c1, 15d
PinConfig M2354/m471/m258/m030g/m0A21: c3, after c2, 15d
NuCodeGen performance: c4, after c3, 15d
PinConfig NUA3500:  
NuCodeGen feedback, M031 series: c5, after c4, 70d 

section ccli
NDA102SD2 (keil/icp auto chip type)           :done, d1, 2020-04, 20d
CP datalog:  done,2020-04, 20d
VBATool UM/RH format: 2020-04, 20d 
nucmd tool m030g/m0a21:done,d2, after d1  ,7d  
nucodegen feedback/UX enhance :d3, after d2  , 50d
m480 spi flash bp jump/remap:  
performance e.g. m031 PLL/ m480ld:  
Help ClockConfifg/Pinconfig related:  

section ychsu
script GPIO/dualcore       : done, e1, 2020-04,13d
m2354 mbed download: done,10d
m030g/m0a21/m471/m479/ml56 pinview: 7d  
m030g :10d         
SD card no M2351/NUC505/M261/M480SPI:14d  
NuBridge2 merge    :25d  
script calls ICE API to control nulink2 GPIO/PWM/ADC:35d  


```




=====

    github opensource auto build and update
    version control git check trm            
    nucodegen auto test system, performance, coverage, add series            
    get customer mail/contact information

    8051 freeIDE
    offline cert export     
    swdlib: power control, general M0 support        
    cross platform ICP

    M487 TRNG for DH key
    cmsisDAPv2 + wcid  
    Estimate test USBH testing time for百佳泰 (if need)
    ETM some function name can't display on nutrace window
    ETM display line of the source code 
    ETM save log to a file
    ETM easy DWT config
    SWO, JTAG

    nucodegen todos
    NuEclipse dual bank/dpm/plm/xom   
    Nueclipse release nulink2 voltage better to be adjusted 
    clockConfig HXT 不能輸入小數 e.g. 22.1184MHz

    new isp protocol, IAP
    isp export/import




