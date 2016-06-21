# A-BRIDGE
Source files for the A-BRIDGE motor driver board


The A-BRIDGE is a dual 3.5A motor driver with built-in LAP signal inverter.


> **Features:**

> - Based on [A4950](http://www.allegromicro.com/~/media/Files/Datasheets/A4950-Datasheet.ashx) full-bridge DMOS PWM driver
> - Control 2 brushed motor with a maximum voltage of 40V
> - Delivers up to 3A per motor (3.5A if dissipated and 5A peack)
> - Built-in inverted PWM signal generator for LAP control with [74HC240](http://www.nxp.com/documents/data_sheet/74HC_HCT240.pdf)

####WARNING: this board should not be used with motor that has a filter capacitor. To know if your motor has filter capacitors see the documentation of your motor, usually the acronym WOC stand for Without capacitors.


 With the PWM LAP control mode you can control both speed and direction with one PWM signal. 

PWM duty-cicle  | Motor 
--------        | ---
0%              | Full Backwards
50%             | Break
100%            | Full Forwards

 When the duty cicle is 50% the motor **brakes**, it's not simply turned off, so the motor still need current to remain blocked. You can disable the bridge using the EN (ENABLE, active LOW) input, that turn off the motor.
PWM LAP needs 2 inverted PWM signals, but with this board you need only a single PWM signal, the inverted one is generated internally using a 74HC240 inverter.

----------

#####A-BRIDGE pinout
<img src="https://raw.githubusercontent.com/tolomeis/A-BRIDGE/master/Resources/Pinout.jpg" width="600">

####Schematic & layout

<img src="https://raw.githubusercontent.com/tolomeis/A-BRIDGE/master/Resources/PCB.png" width="400">

<img src="https://raw.githubusercontent.com/tolomeis/A-BRIDGE/master/Resources/Schematic.png" width="600">
