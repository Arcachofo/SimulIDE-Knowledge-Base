# Linking Components

This feature is not available in version 1.0.0.

## Concept:

Mechanism to link components to perform certain actions:
- Only some component have the ability to link to other components.
- Most component can be linked, but only some can perform actions.
<br>

---

## Can link to other Components:

- **[[Dial]]**
    Calls: 
    *setLinkedValue( (int)v, 0 )*

- **[[Text]] Component**
    Shows value label from linked components.
    Syntax: *$dataN*   (N = component index).

- **[[Led]]**
    Calls: 
    *setLinkedValue( double v, int i )*

- **[[Scripted]]**
    Can call:
    *setLinkedString( string str, int i )*
    *setLinkedValue( double v, int i )*
<br>

---

## Can be linked:

- **[[Dialed]]** ([[Dial]], [[Potentiometer]], [[Variable Resistor]], [[Resistive Sensors]]):
    Called:
    *setLinkedValue( double v, int i=0 )*
    i = 0: set Dial value (0-1000)
    else : set value.

- **[[Text]] Component**
    Called:
    *setLinkedString( QString str, int i )*
    *setLinkedValue( double v, int i )*
    i = 0: set text.
    else : append text.

- **[[7 segment BCD]]**
    Called:
    *setLinkedValue( double v, int i )*
    i = 0: display value.
    else : 1 bit for each segment.

- **[[Clock]] & [[Wave Gen]]**
    Called:
    *setLinkedValue( double v, int i )*
    Set frequency.

- **[[Controlled Source]]**
    Called:
    *setLinkedValue( double v, int i )*
    Set control voltage or current.

- **[[Scripted]]**
    Can be called:
    *setLinkedString( string str, int i )*
    *setLinkedValue( double v, int i )*
<br>

---

## Resources:

- [[Linked Dev]]
- [Forum discussion](https://simulide.forumotion.com/t1556-linking-components)
- Video [Linking Text component to To other components.](https://youtu.be/k7gzxlZPyco)

---

#tutorial