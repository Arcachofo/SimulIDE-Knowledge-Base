# Linking Components

A Component that wants to **link to another** components must:
- Derive from Linkable class.
- Implement context menu action ( TODO: add to Component::ContextMenu).
- Implement code to act on linked components.
- Add hidden property "Links".
- Set m_linkable = true; in constructor.

A component that wants **to do something when linked** must implement one or both:
void setLinkedValue( double v, int i=0 )
void setLinkedString( QString str, int i=0 )
<br>

## Virtual functions:

component.h:
void setLinkedValue( double v, int i=0 )
void setLinkedString( QString str, int i=0 )
void setLinked( bool l )

linkable.h
void createLinks( QList<Component*>* )
void compSelected( Component* comp )

---

## Can link to other Components:

- **[Dial](Dial)**
    Calls: 
    *setLinkedValue( (int)v, 0 )*

- **[Text](Text) Component**
    Shows value label from linked components.
    Syntax: *$dataN*   (N = component index).

- **[Led](Led)** / **[Diode](Diode)**
    Calls: 
    *setLinkedValue( double v, int i )*

- **[Scripted](Scripted)**
    Can call:
    *component.setLinkedString( string str, int i )*
    *component.setLinkedValue( double v, int i )*
<br>

---

## Can be linked:

- **[Dialed](Dialed)** ([Dial](Dial), [Potentiometer](Potentiometer), [Variable Resistor](Variable%20Resistor), [Resistive Sensors](Resistive%20Sensors)):
    Called:
    *setLinkedValue( double v, int i=0 )*
    i = 0: set Dial value (0-1000)
    else : set value.

- **[Text](Text) Component**
    Called:
    *setLinkedString( QString str, int i )*
    *setLinkedValue( double v, int i )*
    i = 0: set text.
    else : append text.

- **[7 segment BCD](7%20segment%20BCD)**
    Called:
    *setLinkedValue( double v, int i )*
    i = 0: display value.
    else : 1 bit for each segment.

- **[Clock](Clock) & [Wave Gen](Wave%20Gen)**
    Called:
    *setLinkedValue( double v, int i )*
    Set frequency.

- **[Capacitor](Capacitor)**
    Called:
    *setLinkedValue( double v, int i )*
    Set capacitance (0 to 1000 = 0 to 100%).

- **[Inductor](Inductor)**
    Called:
    *setLinkedValue( double v, int i )*
    Set inductance (0 to 1000 = 0 to 100%).

- **[Controlled Source](Controlled%20Source)**
    Called:
    *setLinkedValue( double v, int i )*
    Set control voltage or current.

- **[Scripted](Scripted)**
    Can be called:
    *setLinkedString( string str, int i )*
    *setLinkedValue( double v, int i )*

---

#dev