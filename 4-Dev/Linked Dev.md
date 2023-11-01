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

- **[Dial](1-Circuit/Components/11-Other/Dial.md)**
    Calls: 
    *setLinkedValue( (int)v, 0 )*

- **[Text](1-Circuit/Components/10-Graphical/Text.md) Component**
    Shows value label from linked components.
    Syntax: *$dataN*   (N = component index).

- **[Led](1-Circuit/Components/06-Outputs/1-Leds/Led.md)** / **[Diode](1-Circuit/Components/05-Active/1-Rectifiers/Diode.md)**
    Calls: 
    *setLinkedValue( double v, int i )*

- **[Scripted](1-Circuit/Components/Modular%20Components/Scripted/Scripted.md)**
    Can call:
    *component.setLinkedString( string str, int i )*
    *component.setLinkedValue( double v, int i )*
<br>

---

## Can be linked:

- **[Dialed](1-Circuit/Components/Dialed.md)** ([Dial](1-Circuit/Components/11-Other/Dial.md), [Potentiometer](1-Circuit/Components/04-Passive/1-Resistors/Potentiometer.md), [Variable Resistor](1-Circuit/Components/04-Passive/1-Resistors/Variable%20Resistor.md), [Resistive Sensors](1-Circuit/Components/04-Passive/2-Resistive%20Sensors/Resistive%20Sensors.md)):
    Called:
    *setLinkedValue( double v, int i=0 )*
    i = 0: set Dial value (0-1000)
    else : set value.

- **[Text](1-Circuit/Components/10-Graphical/Text.md) Component**
    Called:
    *setLinkedString( QString str, int i )*
    *setLinkedValue( double v, int i )*
    i = 0: set text.
    else : append text.

- **[7 segment BCD](1-Circuit/Components/08-Logic/5-Other%20Logic/7%20segment%20BCD.md)**
    Called:
    *setLinkedValue( double v, int i )*
    i = 0: display value.
    else : 1 bit for each segment.

- **[Clock](1-Circuit/Components/02-Sources/Clock.md) & [Wave Gen](1-Circuit/Components/02-Sources/Wave%20Gen.md)**
    Called:
    *setLinkedValue( double v, int i )*
    Set frequency.

- **[Capacitor](1-Circuit/Components/04-Passive/3-Reactive/Capacitor.md)**
    Called:
    *setLinkedValue( double v, int i )*
    Set capacitance (0 to 1000 = 0 to 100%).

- **[Inductor](1-Circuit/Components/04-Passive/3-Reactive/Inductor.md)**
    Called:
    *setLinkedValue( double v, int i )*
    Set inductance (0 to 1000 = 0 to 100%).

- **[Controlled Source](1-Circuit/Components/02-Sources/Controlled%20Source.md)**
    Called:
    *setLinkedValue( double v, int i )*
    Set control voltage or current.

- **[Scripted](1-Circuit/Components/Modular%20Components/Scripted/Scripted.md)**
    Can be called:
    *setLinkedString( string str, int i )*
    *setLinkedValue( double v, int i )*

---

#dev