# Air_ball

Describes how to make a 3D printed air ball holder with mouse sensors to capture the ball's motion. 

Can be used in behavioral rigs with mice.

# Parts

* 2x Motion sensor PMW3360: https://www.tindie.com/products/jkicklighter/pmw3360-motion-sensor/
* 2x Arduino Micro
* 1x Arduino Due

# How to connect sensors to Micros

Pinout Sensor - Micro:
-------
* MI = MISO
* MO = MOSI
* SS = Slave Select / Chip Select
* SC = SPI Clock
* MT = Motion (active low interrupt line)
* RS = Reset
* GD = Ground
* VI = Voltage in up to +5.5V

https://www.tindie.com/products/jkicklighter/pmw3360-motion-sensor/

# How to connect Micros to Due

We are using the serial ports and the Due provides power.

WARNING: the Due works on 3.3V and the Micros on 5V.

Pinout Due - Micro
-------
* 5V  = Power
* GND = GND
* TX  = RX
* RX  = voltage divider from TX (5V(micro)->3.3V(due), use 2k and 1k resistors)