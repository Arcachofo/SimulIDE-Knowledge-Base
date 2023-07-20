## Concept:
Mechanism to link components to perform certain actions:
- Only some component have the ability to link to other components.
- Most component can be linked, but only some can perform actions.

## Can link to other Components:
- **[[Dial]]**
    Calls: 
    *setLinkedValue( (int)v, 0 )*

- **[[Text Component]]**
    Shows value label from linked components.
    Syntax: *$dataN*   (N = component index).

- **[[Scripted]]**
    Can call:
    *setLinkedString( string str, int i )*
    *setLinkedValue( double v, int i )*

## Can be linked:
- **[[Dialed]]** ([[Dial]], [[Potentiometer]], [[Variable Resistor]], [[Resistive Sensors]]):
    Called:
    *setLinkedValue( double v, int i=0 )*
    i = 0: set Dial value (0-1000)
    else : set value.

- **[[Text Component]]**
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

- **[[Scripted]]**
    Can be called:
    *setLinkedString( string str, int i )*
    *setLinkedValue( double v, int i )*

[[Linked Dev]]


#tutorial