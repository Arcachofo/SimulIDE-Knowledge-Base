# Linking Components

This feature is not available in version 1.0.0.

## Concept:

Mechanism to link components to perform certain actions:
- Only some component have the ability to link to other components.
- Most component can be linked, but only some can perform actions.
<br>

---

## Can link to other Components:

- **[Dial](Components/11-Other/Dial)**
    Send value between Min. Value and Max. Value (in properties)

- **[Text](Components/10-Graphical/Text) Component**
    Shows value label from linked components.
    Syntax: *$dataN*   (N = component index).

- **[Led](Components/06-Outputs/1-Leds/Led)** / **[Diode](Components/05-Active/1-Rectifiers/Diode)**
    Send value of current flowing through.

- **[Dc Motor](Components/06-Outputs/3-Motors/Dc%20Motor)** / **[Stepper](Components/06-Outputs/3-Motors/Stepper)**
    Send angle 0-1000.

- **[Scripted](Components/Modular%20Components/Scripted/Scripted)**
    Can send any value from the script (double or string)
<br>

---

## Can be linked:

- **[Dialed](Components/Dialed)** ([Dial](Components/11-Other/Dial), [Potentiometer](Components/04-Passive/1-Resistors/Potentiometer), [Variable Resistor](Components/04-Passive/1-Resistors/Variable%20Resistor), [Resistive Sensors](Components/04-Passive/2-Resistive%20Sensors/Resistive%20Sensors)):
    Can receive a value (resistance, luminance, etc) or dial position:
    i = 0: set Dial position (0-1000)
    else : set resistance value.

- **[Text](Components/10-Graphical/Text) Component**
    Can append or set text:
    i = 0: set text.
    else : append text.

- **[7 segment BCD](Components/08-Logic/5-Other%20Logic/7%20segment%20BCD)**
    Can receive a display value or segment on/off:
    i = 0: display value (0-F).
    else : 1 bit for each segment.

- **[Clock](Components/02-Sources/Clock) & [Wave Gen](Components/02-Sources/Wave%20Gen)**
    Can receive a frequency value.

- **[Capacitor](Components/04-Passive/3-Reactive/Capacitor)**
    Can receive a percentage capacitance (0 to 1000 = 0 to 100%).

- **[Inductor](Components/04-Passive/3-Reactive/Inductor)**
    Can receive a  percentage inductance (0 to 1000 = 0 to 100%).

- **[Controlled Source](Components/02-Sources/Controlled%20Source)**
    Can receive a control voltage or current.

- **[Scripted](Components/Modular%20Components/Scripted/Scripted)**
    Can receive a double or string value.
<br>

---

## Resources:

- [Linked Dev](../4-Dev/Linked%20Dev)
- [Forum discussion](https://simulide.forumotion.com/t1556-linking-components)
- Video [Linking Text component to To other components.](https://youtu.be/k7gzxlZPyco)

---

#tutorial