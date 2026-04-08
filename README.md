# xmos_xu316_cs43131_usb_aud

> [!WARNING]  
> Do not order pcb directly with my current kicad project!

## PCB errors to fix

* refer to xu316 datasheet, redraw the oscillator circuit correctly, current version did not include the 1M resistor between XTI and XTO
* connect the mclk from dac to X0D11 and X1D11, currently the mclk is connected to a wrong pin, X1D09

## Firmware Compilation Steps

* install xmos xtc tools vscode extension
* clone (https://github.com/youheng7185/sw_usb_audio.git)
* open with vscode, try building
* after getting error from lib_board_support, delete the lib_board_support and clone this (https://github.com/youheng7185/lib_board_support) into that directory
* when build finishes, run ```./pack.sh``` to generate the rom for qspi flash
* flash qspi flash with ```output.bin```

## Reference

* Bric for its cs43131 schematics and init sequence (https://github.com/zephray/Bric)
* Blog by WuXi for cs43131 registers (https://wuxiproj.mzy7.cn/posts/a75c0c32)

## Main Component
* XU316-1024-QF60B-C24
* STMicro USB6B1 USB ESD protection
* Generic USB-C 2.0 TH port
* Winbond W25Q64JVS
* Seiko Epson FA-238 (24 Mhz)
* TI TPS563201 (1.8v dcdc), this requires a 252012 size 2.2uH inductor
* RT9013-33GB, 3.3v ldo
* RT9013-18GB, 1.8v ldo (x4, notes: inside the schematics, 1.8v ldo also uses 3.3v ldo symbol)
* NDK NZ2520SDA-24.576MHZ
* Cirrus Logic CS43131-CNZR
* PJ-327A0-SMT (audio jack)
* TI PCA9306DCUR
* TI SN74AVC4T774PWR
* common values of resistor and capacitor

## Pictures

![audio_settings](https://github.com/user-attachments/assets/eeb48e43-d560-43f8-a122-932cf3b8a2dc)
![20260408_190845](https://github.com/user-attachments/assets/8dfcfa9a-3adc-466c-8341-06d167435b70)



