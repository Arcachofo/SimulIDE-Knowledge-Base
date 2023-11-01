# Linking Components

This feature is not available in version 1.0.0.

## Concept:

Mechanism to link components to perform certain actions:
- Only some component have the ability to link to other components.
- Most component can be linked, but only some can perform actions.
<br>

---

## Can link to other Components:

- **[Dial](1-Circuit/Components/11-Other/Dial.md)**
    Send value between Min. Value and Max. Value (in properties)

- **[Text](1-Circuit/Components/10-Graphical/Text.md) Component**
    Shows value label from linked components.
    Syntax: *$dataN*   (N = component index).

- **[Led](1-Circuit/Components/06-Outputs/1-Leds/Led.md)** / **[Diode](1-Circuit/Components/05-Active/1-Rectifiers/Diode.md)**
    Send value of current flowing through.

- **[Dc Motor](1-Circuit/Components/06-Outputs/3-Motors/Dc%20Motor.md)** / **[Stepper](1-Circuit/Components/06-Outputs/3-Motors/Stepper.md)**
    Send angle 0-1000.

- **[Scripted](1-Circuit/Components/Modular%20Components/Scripted/Scripted.md)**
    Can send any value from the script (double or string)
<br>

---

## Can be linked:

- **[Dialed](1-Circuit/Components/Dialed.md)** ([Dial](1-Circuit/Components/11-Other/Dial.md), [Potentiometer](1-Circuit/Components/04-Passive/1-Resistors/Potentiometer.md), [Variable Resistor](1-Circuit/Components/04-Passive/1-Resistors/Variable%20Resistor.md), [Resistive Sensors](1-Circuit/Components/04-Passive/2-Resistive%20Sensors/Resistive%20Sensors.md)):
    Can receive a value (resistance, luminance, etc) or dial position:
    i = 0: set Dial position (0-1000)
    else : set resistance value.

- **[Text](1-Circuit/Components/10-Graphical/Text.md) Component**
    Can append or set text:
    i = 0: set text.
    else : append text.

- **[7 segment BCD](1-Circuit/Components/08-Logic/5-Other%20Logic/7%20segment%20BCD.md)**
    Can receive a display value or segment on/off:
    i = 0: display value (0-F).
    else : 1 bit for each segment.

- **[Clock](1-Circuit/Components/02-Sources/Clock.md) & [Wave Gen](1-Circuit/Components/02-Sources/Wave%20Gen.md)**
    Can receive a frequency value.

- **[Capacitor](1-Circuit/Components/04-Passive/3-Reactive/Capacitor.md)**
    Can receive a percentage capacitance (0 to 1000 = 0 to 100%).

- **[Inductor](1-Circuit/Components/04-Passive/3-Reactive/Inductor.md)**
    Can receive a  percentage inductance (0 to 1000 = 0 to 100%).

- **[Controlled Source](1-Circuit/Components/02-Sources/Controlled%20Source.md)**
    Can receive a control voltage or current.

- **[Scripted](1-Circuit/Components/Modular%20Components/Scripted/Scripted.md)**
    Can receive a double or string value.
<br>

---

## Resources:

- [Linked Dev](4-Dev/Linked%20Dev.md)
- [Forum discussion](https://simulide.forumotion.com/t1556-linking-components)
- Video [Linking Text component to To other components.](https://youtu.be/k7gzxlZPyco)

---

#tutorial