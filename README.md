# Air_ball

Describes how to make a 3D printed air ball holder with mouse sensors to capture the ball's motion. 

Can be used in behavioral rigs with mice.

[![Demo CountPages airball](https://img.youtube.com/vi/CR8DfGOpQPQ/hqdefault.jpg)](https://www.youtube.com/watch?v=CR8DfGOpQPQ)

## Parts

* 3D printed parts: bottom and top
* M6 thread heat-insert: https://befr.rs-online.com/web/p/threaded-inserts/0278629/
* M4 thread heat-insert: https://befr.rs-online.com/web/p/threaded-inserts/0278607/
* M6 pneumatic push-in fitting: https://befr.rs-online.com/web/p/pneumatic-straight-fittings/1216041/
* Pressure regulator : SMC pneumatics - Model: ARM11A B3-208-J1: 
https://www.smc.eu/portal_ssl/WebContent/digital_catalog_2/jsp/view_product_configurator.jsp?dc_product_id=87018&part_number=ARM11AB3-508-J1
* 6mm tubing: https://www.smc.eu/portal_ssl/WebContent/digital_catalog_2/jsp/view_product_configurator.jsp?dc_product_id=54694&lang=fr&ctry=BE
* Warning: this assumes you have a source for pressured air

## How to assemble

* 3D print the components (black PLA)
* Heat-insert M4-M6 threads in the 3D parts with a soldering iron
* Put an M6 push-in fitting in the only hole that goes through the plastic
* Use epoxy to glue bottom and top parts

# Motion Sensors 
## Parts

* 2x 3D printed parts: sensor holder 
* 2x Motion sensor PMW3360: https://www.tindie.com/products/jkicklighter/pmw3360-motion-sensor/
* 2x Arduino Micro
* 1x Arduino Due
* 1x PCB

## Power

Both board types take 12V on Vin and share the same GND.

## How to connect sensors to Micros

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

## How to connect Micros to Due

We are using the serial ports and the Due provides power.

WARNING: the Due works on 3.3V and the Micros on 5V.

Pinout Due - Micro
-------
* RX  = voltage divider from TX (5V(micro)->3.3V(due), use 2k and 1k resistors)

# Micro's output

XY motion from the sensor, sampled at around 1kHz

# Due's output

Yaw - pitch - roll values (you can add eventual other outputs like the total distance)