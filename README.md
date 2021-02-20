# M031BSP_IAP
 M031BSP_IAP

update @ 2021/02/20

1. under APROM , with 2 project (boot loader and application)

2. under application project , there 2 define APP_01/ APP_02 , KEILC R/O base : 0x00004000

compile project and get APP_01 and APP_02 binary file , for boot loader project : USE_MANUAL_UPDATE_FW

programming with ICP tool , APP_01 address : 0x00010000 , APP_02 address : 0x00012000

3. under boot loader project , two define (USE_EMULATE_AUTO_JUMP , USE_MANUAL_UPDATE_FW) 

to test auto jump , from boot loader to application 

3. under USE_EMULATE_AUTO_JUMP , when power on from boot loader project , 

if no trigger update firmware flow (flag_update_fw) , after timeout will jump to application code

![image](https://github.com/released/M031BSP_IAP/blob/main/bootloader_timeout.jpg)

4. under USE_MANUAL_UPDATE_FW  , when power on from boot loader project , 

will wait for update firmware , by press 1 / 2 to select application code update

![image](https://github.com/released/M031BSP_IAP/blob/main/bootloader.jpg)

![image](https://github.com/released/M031BSP_IAP/blob/main/app01.jpg)

![image](https://github.com/released/M031BSP_IAP/blob/main/app02.jpg)

5. under application code , press z/Z/x/X , will jump to boot loader (same as nRESET pin)

