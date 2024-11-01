**Minimum version: 1.1.0-SR1.**

Digital Potentiometer with SPI interface. <br>

![[spi_digipot.png]]

<br>
This is a subcircuit containing a Potentiometer and a Script Component controlling it.<br>
The Script Component implements the SPI interface and the Component properties.<br>
Bytes received are used to set the value of the Potentiometer.<br>

This Component is usually connected to a Microcontroller that sends data to it:<br>

![[spi_dp_test.png]]

<br>

## Properties:

### Main:
**- Steps:** (256) <br>
   Ladder steps of the Potentiometer.<br>
   Maximum value is 256 (1 byte).<br>

**- Resistance:** (100 kΩ) <br>
   Potentiometer Resistance.<br>