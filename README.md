# LED garland programming on AVR microcontoller
The goal of this project was to study the AVR microcontollers. The following is a [CodeVisionAVR](https://www.codevision.be/) project that can be used to build a new firmware for the microcontroller. As a SPICE system to simulate the circute you can use the [Proteus](https://www.labcenter.com/) project that is already configured.

## Components
The circute consists of 8 red LED (2.2V, 10mA), 8 resistors (300 OHM), power source (5V), button, ground and a ATtiny2313 microcontroller.
![attiny2313.png](attiny2313.png)

## Demo
The program should simulate a loop of running lights, pushing the button makes it change the direction.


![demo.gif](demo.gif)

## Compile
The most optimal way is to use the CodeVisionAVR or AVR Studio to build the project, but you can still compile it in Linux. You must install the following libs:
```bash
apt-get install avr-libc
apt-get install gcc-avr
```
After installation execute the following commands:
```bash
# Create ELF executable
avr-gcc -mmcu=attiny2313 -Os -DF_CPU=1000000UL -Wall -std=gnu99 -o main.elf main.c
# Convert it to HEX firmware
avr-objcopy -O ihex -R .eeprom main.elf main.hex
```

## Resources
- [ATtiny2313](ATTINY2313.pdf)