**Minimum version: 1.1.0-SR1.**<br>

16 segment display. <br>

![[16seg.png]]

<br>
It can be multiplexed and PWM. <br>
But it doesn't match LED electric characteristics. <br>
It works like a Logic Component with High Impedance inputs. <br>

To use this Component, connect the Data Pin to a bus.<br>
Common pin should be connected to ground if configured as common cathode or +5V otherwise.<br>

![[16_seg_test.png]]

<br>

### Pins:
**- D: data pin**. <br>
   16 bit Bus pin driving the segments (except dot). <br>

**- p: dot pin.** <br>
   This pin drives the dot segment. <br>

**- C: common pin.** <br>
   In Common Cathode mode drive it Low to activate. <br>
   In Common Anode mode drive it High to activate. <br>

<br>

## Properties:

### Main:
**- Common Cathode:** (yes) <br>
   Determines if common cathode or common anode. <br>