# EmonESP

[![Build Status](https://travis-ci.org/openenergymonitor/EmonESP.svg?branch=master)](https://travis-ci.org/openenergymonitor/EmonESP)

ESP8266 WIFI serial to emoncms link

![EmonEsp WiFi AP Setup Portal](docs/emonesp.jpg)

## Installation

EmonESP used [ESP8266 Arduino core](https://github.com/esp8266/Arduino)

Firmware can be compiled and uploaded either using PlatfomIO ([see blog post](https://blog.openenergymonitor.org/2016/06/platformio/)) or Arduino IDE.


### Option 1: Using PlatformIO

For more detailed ESP8266 Arduino core specific PlatfomIO notes see: https://github.com/esp8266/Arduino#using-platformio

#### 1a. Install PlatformIO command line

The easiest way if running Linux is to install use the install script, this installed pio via python pip and installs pip if not present. See [PlatformIO installation docs](http://docs.platformio.org/en/latest/installation.html#installer-script). Or PlatformIO IDE can be used :

`$ sudo python -c "$(curl -fsSL https://raw.githubusercontent.com/platformio/platformio/master/scripts/get-platformio.py)"`

#### 1b. And / Or use PlatformIO IDE

Standalone built on GitHub Atom IDE, or use PlatformIO Atom IDE plug-in if you already have Atom installed. The IDE is nice, easy and self-explanitory.

[Download PlatfomIO IDE](http://platformio.org/platformio-ide),

#### 2. Clone this repo

`$ git clone https://github.com/openenergymonitor/EmonESP`

#### 3. Compile

```
$ cd EmonESP
$ pio run
```

The first time platformIO is ran the espressif arduino tool chain and all the required libs will be installed if required.


#### 3. Upload

##### a.) Upload main program:

`$ pio run -t upload`

##### b.) Upload data folder to the file system (html, css etc.) (SPIFFS):

`$ pio run -t uploadfs`

See [PlatfomrIO docs regarding SPIFFS uploading ](http://docs.platformio.org/en/latest/platforms/espressif.html#uploading-files-to-file-system-spiffs)

***

### Option 2: Using Arduino IDE

#### 1. Install ESP for Arduino with Boards Manager

Install steps from: https://github.com/esp8266/Arduino

Starting with 1.6.4, Arduino allows installation of third-party platform packages using Boards Manager. ESP Arduino packages are available for Windows, Mac OS, and Linux (32 and 64 bit).

- Install Arduino 1.6.8 from the Arduino website.
- Start Arduino and open Preferences window.
- Enter http://arduino.esp8266.com/stable/package_esp8266com_index.json into Additional Board Manager URLs field. You can add multiple URLs, separating them with commas.
- Open Boards Manager from Tools > Board menu and install esp8266 platform (and don't forget to select your ESP8266 board from Tools > Board menu after installation).

#### 2. Install ESP filesystem file uploader

From: https://github.com/esp8266/Arduino/blob/master/doc/filesystem.md

- Download the tool: https://github.com/esp8266/arduino-esp8266fs-plugin/releases/download/0.2.0/ESP8266FS-0.2.0.zip.
- In your Arduino sketchbook directory, create tools directory if it doesn't exist yet
- Unpack the tool into tools directory (the path will look like <home_dir>/Arduino/tools/ESP8266FS/tool/esp8266fs.jar)
- Restart Arduino


#### 3. Clone this repo

`$ git clone https://github.com/openenergymonitor/EmonESP`

#### 4. Compile and Upload

- Open src/src.ino in the Arduino IDE.
- **Upload main sketch:** Compile and Upload as normal using Arduino IDE [CTRL + u]
- **Upload 'data' folder**: Upload data folder (home.html web page etc) using `tools > ESP8266 Sketch Data Upload tool`.

***

### Licence

GNU General Public License
