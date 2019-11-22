# Air_ball

Describes how to make a 3D printed air ball holder with mouse sensors to capture the ball's motion. 

Can be used in behavioral rigs with mice.

[![Demo CountPages airball](https://img.youtube.com/vi/CR8DfGOpQPQ/hqdefault.jpg)](https://www.youtube.com/watch?v=CR8DfGOpQPQ)


# Parts

* 2x Motion sensor PMW3360: https://www.tindie.com/products/jkicklighter/pmw3360-motion-sensor/
* 2x Arduino Micro
* 1x Arduino Due

# Power

All boards take 12V on Vin and share the same GND.

# How to connect sensors to Micros

Pinout Sensor - Micro:
-------
* RS --- (NONE)
* GD --- GND
* MT --- Pin 7 (PE6, INT6) -> movement interrupt
* SS --- Pin 10 (PB6)
* SC --- SCK (PB1)
* MO --- MOSI (PB2)
* MI --- MISO (PB3)
* VI --- 5V

https://www.tindie.com/products/jkicklighter/pmw3360-motion-sensor/

# How to connect Micros to Due

We are using the serial ports and the Due provides power.

WARNING: the Due works on 3.3V and the Micros on 5V.

Pinout Due - Micro
-------
* TX  = RX
* RX  = voltage divider from TX (5V(micro)->3.3V(due), use 2k and 1k resistors)

