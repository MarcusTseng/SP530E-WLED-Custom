Update to 0.15.0  

# WLED Build For SP530E  
Prepare UART Converter  (be aware of the driver, C210x, CH340)
Download custom_build.bin  
Download ESPtool [Here](https://github.com/espressif/esptool/releases)  
Download C3_bootloader.bin and C3_partitions_4M.bin [Here](https://github.com/Aircoookie/WLED/releases/tag/v0.15.0-b2)  

### Connect UART Cable to board's reverse side  

### Use this Command below to backup the original firmware.  
```
./esptool read_flash 0 0x400000 sp530e-encrypted.bin  
```

### Use this Command below to flash the custom firmware.  
```
./esptool write_flash --encrypt 0x0 C3_bootloader.bin 0x8000 C3_partitions_4M.bin 0x10000 custom_build.bin  
```

### I/O Pins:  
On Board Button GPIO 8  
On Board Mic GPIO 3  ( [not supported in WLED](https://github.com/wled/WLED/blob/main/usermods/audioreactive/readme.md#supported-mcus) )
On Board Blue LED GPIO 0 (Inverted) 
On Board Green LED GPIO 1 (Inverted)  
  (Add an output in WLED on the above GPIO and set it.)
LED DAT Output GPIO 19  

### Analog Pins:  
R: GPIO 10  
G: GPIO 7  
B: GPIO 6  
WW: GPIO 5  
CW: GPIO 4 


##FCOB CCT
