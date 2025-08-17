# Binary_clock
A binary clock made with ESP8266 and WS2812

[Web Installer here](https://no-cqrt.github.io/Binary_clock/)


## About the project:
This is a simple project to create a binary clock using a ESP8266 and some WS2812 single addressable leds.
Use the wi-fi connection to syncronize the time via NTP, change timezone, led color and brightness via Serial commands or physical buttons.
In this case, i've used two "touch" button behind the front mask (STL for [box](https://github.com/No-CQRT/Binary_clock/blob/main/STL/Binary_clock_case.stl) and [mask](https://github.com/No-CQRT/Binary_clock/blob/main/STL/Binary_clock_front.stl) attached) for a better, minimal design.


## Hardware
- 1 WEMOS D1 ESP8266 (or similar)
- 20 WS2812 RGB single addressable led
- 2 (or 3) buttons for color change,brightness and timezone
- USB cable, soldering, various cables


## Installation

1) Download the firmware form the [release](https://github.com/No-CQRT/Binary_clock/releases/tag/v1.0) link and install with your favourite tool
2) Use the [Web Installer here](https://no-cqrt.github.io/Binary_clock/)
3) Download source, open it in platform.io, build and upload.

## Post installation instruction

After the installation, is suggested to connect the web installer, press the 
To connect to wi-fi, use the "logs and console" section to access serial interface and press a "reset device" to see the clean serial interface with commands.

To connect to wifi use these commands:
```
ssid:your_wifi_ssid
```
and
```
pass:password
```
> [!IMPORTANT]  
> please note: type ssid: and pass: with colon and ***no space*** before the value like in the example before

## Commands

If you have connected the physical buttons, you can change color, brightness and time zone in a click (cycling).
Or you can connect via serial console (also via web installer) and type:
```
ccolor
```
to change the colors
```
cbrig
```
to change the brightness   
```
tzplus
```
to change the timezone (+1)
```
tzminus
```
to change the timezone (-1)

After the first connection, is suggested to adjust the timezone, all parameters will be stored in eprom.


### Cabling
The strip is attached to D4 like the schema below

<img width="794" height="1123" alt="binary_clock" src="https://github.com/user-attachments/assets/58da41b1-4483-4b92-a7aa-1b54910e49e8" />


### LED Schema

The 20 LEDs are used to display the time in this format: HH,MM,SS (note: time is in format 24h)
first two columns are for hours, second two for minutes, and the last two with seconds

Pay attention at the LED sequence: in a ideal 20 LED strip, the time will be represented as below

<img width="1123" height="794" alt="binary_clock_2" src="https://github.com/user-attachments/assets/ef45fd9e-9f39-43e0-b2a4-845ad40e4b11" />

So the "weight" of the bit will be displayed from below (1) to top (8) in sequence 1,2,4,8. first colum need ony 2 led, so also decimal for minutes and seconds need only 3.

You can build your case or use the provided STL to have a prototype like below:

![PXL_20250816_143031252 PORTRAIT](https://github.com/user-attachments/assets/3b3a8fae-7553-4096-a9aa-35924824f211)
![PXL_20250816_143007586 PORTRAIT](https://github.com/user-attachments/assets/20b577b0-31f9-4448-aaaf-276b160a1acf)
![PXL_20250816_142951659 PORTRAIT](https://github.com/user-attachments/assets/24d29600-fe0f-4e0a-8f07-efc343a496f6)

and a "live" example here


https://github.com/user-attachments/assets/fe3e8189-b0d6-4bda-aca8-0861012bbe0b





