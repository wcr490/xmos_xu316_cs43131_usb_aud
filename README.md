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
