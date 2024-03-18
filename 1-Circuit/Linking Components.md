This feature is only available from version 1.1.0.

When you link two or more component, the "active" one will perform some action over the linked components, usually sending some data. <br>

For example you can link a dial to several potentiometers, then when you adjust the dial all the linked potentiometers will be automatically adjusted to the same position.

- Only some components have the ability to link to other components.
- Most component can be linked, but only some can perform actions.

---

## Can link to other Components:

- **[[Dial]]**<br>
    Send value between Min. Value and Max. Value (in properties)

- **[[Text]] Component**<br>
    Shows value label from linked components.<br>
    Syntax: *$dataN*   (N = component index).<br>

- **[[Led]]** / **[[Diode]]**<br>
    Send value of current flowing through (for 40 mA it sends 0.040).<br>

- **[[Dc Motor]]**<br>
    Send value 0 to 1000 corresponding to rotation angle (1000 = 360º)<br>

- **[[Stepper]]**<br>
    Send value 0 to 1000 corresponding to rotation angle (1000 = 360º)<br>

- **[[Scripted]]**<br>
    Can send any value from the script (double or string)<br>
---

## Can be linked:

- **[[Dialed]]** ([[Dial]], [[Potentiometer]], [[Variable Resistor]], [[Resistive Sensors]]):<br>
    Can receive a value (resistance, luminance, etc) or dial position:<br>
    i = 0: set Dial position (0-1000)<br>
    else : set resistance value.<br>

- **[[Text]] Component**<br>
    Can append or set text:<br>
    i = 0: set text.<br>
    else : append text.<br>

- **[[7 segment BCD]]**<br>
    Can receive a display value or segment on/off:<br>
    i = 0: display value (0-F).<br>
    else : 1 bit for each segment.<br>

- **[[Clock]] & [[Wave Gen]]**<br>
    Can receive a frequency value.<br>

- **[[Capacitor]]**<br>
    Can receive a percentage capacitance (0 to 1000 = 0 to 100%).<br>

- **[[Inductor]]**<br>
    Can receive a  percentage inductance (0 to 1000 = 0 to 100%).<br>

- **[[Controlled Source]]**<br>
    Can receive a control voltage or current.<br>

- **[[Scripted]]**<br>
    Can receive a double or string value.<br>

---

## Resources:

- [[Linked Dev]]
- [Forum discussion](https://simulide.forumotion.com/t1556-linking-components)
- Video [Linking Text component to To other components.](https://youtu.be/k7gzxlZPyco)

---
