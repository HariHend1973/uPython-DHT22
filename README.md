uPython-DHT22
=============

This module provides a device driver for DHT22 (or DHT11 or AM2302) sensors on microPython board.

You can check more about these temperature and humidity sensors at the following page: http://www.adafruit.com/products/385

You can check more about the microPython project here: http://micropython.org/

Wiring
------

The basic wiring is designed to use no additional parts (like a pull-up resistor) and can be directly put to the microPython board.
The wiring:

```
Sensor pin | board pin
-----------+----------
    VDD    |    Y1
    DTA    |    Y2
    NC     |    Y3
    GND    |    Y4
```

You can check photos, how it is plugged in at [this page](https://plus.google.com/photos/107569319719026103290/albums/6045166919384621489?authkey=CPaD1-25hPrx5AE).

Installation
------------
There are two files:
* DHT22.py - the module implementing communication with the sensor
* main.py  - a sample file how to use the module (to use it you will need LCD panel installed)

The simplest installation way is to follow these steps (Linux):

1. Connect your microPython board to your PC using a USB cable
2. Mount the device pointing to the board (/dev/sdb1 in my case)
  ```
  mkdir ~/tmp
  sudo mount /dev/sdb1 ~/tmp
  ```
3. copy DHT22.py and main.py files to the board
  ```
  sudo cp DHT22.py main.py ~/tmp
  ```
4. Unmount the device
  ```
  sudo umount ~/tmp
  ```
5. Restart your microPython board


uPython-DHT
===========
universal library for DHT11, DHT21 and DHT22

Installation
------------
There are one files:
* dht.py - the module implementing communication with the sensor
copy on the uPython.

Hardware
--------
```
Sensor pin | board pin
-----------+----------
    Pin1 VDD    |    3.3V
    Pin2 DTA    |    Y9 (or other Data-Pin)
    Pin3 NC     |    not conect
    Pin4 GND    |    GND
```

usage
-----
on the console (Putty):
import dht
dht.init()
#default timer_id = 2, data_pin = 'Y9', the_dhttype='DHT11'

dht.measure()  
#give the (humidity, temperature)

dht.hum()  
#give the humidity

dht temp() 
#give the temperature

