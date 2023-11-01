# Linking Components

This feature is not available in version 1.0.0.

## Concept:

Mechanism to link components to perform certain actions:
- Only some component have the ability to link to other components.
- Most component can be linked, but only some can perform actions.
<br>

---

## Can link to other Components:

- **[Dial](Dial)**
    Send value between Min. Value and Max. Value (in properties)

- **[Text](Text) Component**
    Shows value label from linked components.
    Syntax: *$dataN*   (N = component index).

- **[Led](Led)** / **[Diode](Diode)**
    Send value of current flowing through.

- **[Dc Motor](Dc%20Motor)** / **[Stepper](Stepper)**
    Send angle 0-1000.

- **[Scripted](Scripted)**
    Can send any value from the script (double or string)
<br>

---

## Can be linked:

- **[Dialed](Dialed)** ([Dial](Dial), [Potentiometer](Potentiometer), [Variable Resistor](Variable%20Resistor), [Resistive Sensors](Resistive%20Sensors)):
    Can receive a value (resistance, luminance, etc) or dial position:
    i = 0: set Dial position (0-1000)
    else : set resistance value.

- **[Text](Text) Component**
    Can append or set text:
    i = 0: set text.
    else : append text.

- **[7 segment BCD](7%20segment%20BCD)**
    Can receive a display value or segment on/off:
    i = 0: display value (0-F).
    else : 1 bit for each segment.

- **[Clock](Clock) & [Wave Gen](Wave%20Gen)**
    Can receive a frequency value.

- **[Capacitor](Capacitor)**
    Can receive a percentage capacitance (0 to 1000 = 0 to 100%).

- **[Inductor](Inductor)**
    Can receive a  percentage inductance (0 to 1000 = 0 to 100%).

- **[Controlled Source](Controlled%20Source)**
    Can receive a control voltage or current.

- **[Scripted](Scripted)**
    Can receive a double or string value.
<br>

---

## Resources:

- [Linked Dev](Linked%20Dev)
- [Forum discussion](https://simulide.forumotion.com/t1556-linking-components)
- Video [Linking Text component to To other components.](https://youtu.be/k7gzxlZPyco)

---

#tutorial