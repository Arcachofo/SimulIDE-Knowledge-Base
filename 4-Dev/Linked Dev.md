A Component that wants to **link to another** components must:<br>
- Derive from Linkable class.
- Implement context menu action ( TODO: add to Component::ContextMenu).
- Implement code to act on linked components.
- Add hidden property "Links".
- Set m_linkable = true; in constructor.

A component that wants **to do something when linked** must implement one or both:<br>
void setLinkedValue( double v, int i=0 )<br>
void setLinkedString( QString str, int i=0 )<br>


## Virtual functions:

component.h:<br>
void setLinkedValue( double v, int i=0 )<br>
void setLinkedString( QString str, int i=0 )<br>
void setLinked( bool l )<br>

linkable.h<br>
void createLinks( QList<Component*>* )<br>
void compSelected( Component* comp )<br>

---

## Can link to other Components:

- **[[Dial]]**
    Calls: <br>
    *setLinkedValue( (int)v, 0 )*<br>

- **[[Text]] Component**
    Shows value label from linked components.<br>
    Syntax: *$dataN*   (N = component index).<br>

- **[[Led]]** / **[[Diode]]**
    Calls: <br>
    *setLinkedValue( double v, int i )*<br>

- **[[Scripted]]**
    Can call:<br>
    *component.setLinkedString( string str, int i )*<br>
    *component.setLinkedValue( double v, int i )*<br>

---

## Can be linked:

- **[[Dialed]]** ([[Dial]], [[Potentiometer]], [[Variable Resistor]], [[Resistive Sensors]]):
    Called:<br>
    *setLinkedValue( double v, int i=0 )*<br>
    i = 0: set Dial value (0-1000)<br>
    else : set value.<br>

- **[[Text]] Component**
    Called:<br>
    *setLinkedString( QString str, int i )*<br>
    *setLinkedValue( double v, int i )*<br>
    i = 0: set text.<br>
    else : append text.<br>

- **[[7 segment BCD]]**
    Called:<br>
    *setLinkedValue( double v, int i )*<br>
    i = 0: display value.<br>
    else : 1 bit for each segment.<br>

- **[[Clock]] & [[Wave Gen]]**
    Called:<br>
    *setLinkedValue( double v, int i )*<br>
    Set frequency.<br>

- **[[Capacitor]]**
    Called:<br>
    *setLinkedValue( double v, int i )*<br>
    Set capacitance (0 to 1000 = 0 to 100%).<br>

- **[[Inductor]]**
    Called:<br>
    *setLinkedValue( double v, int i )*<br>
    Set inductance (0 to 1000 = 0 to 100%).<br>

- **[[Controlled Source]]**
    Called:<br>
    *setLinkedValue( double v, int i )*<br>
    Set control voltage or current.<br>

- **[[Scripted]]**
    Can be called:<br>
    *setLinkedString( string str, int i )*<br>
    *setLinkedValue( double v, int i )*<br>

---
