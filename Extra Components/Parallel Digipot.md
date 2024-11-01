**Minimum version: 1.1.0-SR1.**<br>

Digital Potentiometer with I2C interface. <br>

![[parallel_digipot.png]]

<br>
This is a subcircuit containing a Potentiometer and a Script Component controlling it.<br>
The Script Component implements a 16 bit Port and the Component properties.<br>
Data present at the Input Port is used to set the value of the Potentiometer.<br>

To use this Component, connect the Data Pin to a bus:

![[par-dp-test.png]]

<br>

### Pins:
**- Data:** data pin.<br>
   16 bit Bus pin for input data.<br>

**- !CS:** Chip Select pin.<br>
   Active Low.<br>

<br>

## Properties:

### Main:
**- Bits:** (6)
   Size of the parallel interface and Potentiometer steps.<br>
   Maximum size: 16 bits.<br>

**- Resistance:** (100 kΩ) <br>
   Potentiometer Resistance.<br>