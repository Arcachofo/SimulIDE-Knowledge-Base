# Scripted Components
(This feature is not available in version 1.0.0)

With Scripted Components it is possible to define the behaviour of the device in a script.

Scripted components are a type of [Modular](../Modular) Components, with an extra file containing the script.

Creating an Scripted component involves these steps:

1. [](../../11-Other/Package#Creating%20Package%20File|Creating%20Package%20File.)
2. [#Creating Definition file.](#Creating%20Definition%20file.)
3. [#Creating Script file.](#Creating%20Script%20file.)
4. [#Creating component folder](#Creating%20component%20folder) with all files.
5. [](../Modular#Add%20to%20component%20list|Add%20to%20component%20list.)

---

# Creating Definition file.

This file describes which kind of component it is and the  parts or modules it contains.

For example, in the file below we can see that **core**  is set to *"scripted"* , so this is an Scripted  component, and the **script** is in *"file.as"* :

```xml
    <iou name="comp_name" core="scripted" script="file.as" >

      <properties name="group name">
        <property name="prop1" type="double" />
        <property name="prop2" type="uint"   />
      </properties>

      <ioport name="PORTA" pins="A,B,C,D,E,F" />

    </iou>
```

We can also see That there is a property group with 2 properties and an IO Port with 4 pins.

**Script must implement property getters and setters:**

```c
    void setProp1( double val )
    double getProp1()
    void setProp2( uint val )
    uint getProp2()
```
<br>

---

# Creating Script file.

This is a program written in [#The script language](#The%20script%20language) describing the behavior of the component.

Script files must have extension .as and use the name defined in the definition file.

---

## Script functions called from C++.

These are functions you can implement in the script.

```c
    void setup()
    void reset()
    void voltChanged()
    void updateStep()
    void runEvent()
    void extClock( bool clkState )
    int getCpuReg( string name )
    string getStrReg( string name )
    void command( string c )
    void setLinkedValue( int val, int i )
    void setLinkedString( string str, int i )
    void INTERRUPT( uint vector )
```

---

## Available C++ functions to call from the script.

```c
    void print( string &msg )
```

### Component:

```c
    IoPort@  getPort( string port )
    IoPin@   getPin( string pin )
    McuPort@ getMcuPort( string port )
    McuPin@  getMcuPin( string pin )

    void addCpuReg( string name, string type )
    void addCpuVar( string name, string type )

    void toConsole( string msg )  // To Delete
    void showValue( string val )

    void addEvent( uint time_ps )
    void cancelEvents()
    uint64 circTime()

    int  readPGM( uint addr )
    void writePGM( uint addr, int val )
    int  readRAM( uint addr )
    void writeRAM( uint addr, int val )
    int  readROM( uint addr )
    void writeROM( uint addr, int val )

    void INTERRUPT( uint vector )

    string getPropStr( int index, string name )
    void setLinkedValue( int index, int val, int i )
    void setLinkedString( int index, string val, int i )
```

### IoPort@.

```c
    void setPinMode( uint mode )
    uint getInpState()
    void setOutState( uint state )
    void changeCallBack( eElement@ e, bool en )
```

### IoPin@.

```c
    void setPinMode( uint mode )
    void setOutState( bool state )
    bool getInpState()
    double getVoltage()
    void setVoltage( double volt )
    void changeCallBack( eElement@ e, bool en )
```

### McuPort@.

```c
    void controlPort( bool outCtrl, bool dirCtrl )
    void setDirection( uint dir )
    uint getInpState()
    void setOutState( uint state )
```

### McuPin@.

```c
    void setDirection( bool dir )
    void setPortState( bool state )
    void controlPin( bool outCtrl, bool dirCtrl )
    void setExtInt( uint mode )
    void setPinMode( uint mode )
    bool getInpState()
    void setOutState( bool state )
    double getVoltage()
    void setVoltage( double volt )
    void changeCallBack( eElement@ e, bool en )
```

---
# The script language

https://www.angelcode.com/angelscript/sdk/docs/manual/doc_script.html

[Arrays](Arrays)


---

# Resources:

- [Forum discussion,](https://simulide.forumotion.com/t990-scripted-components)
- Video (english): [Creating Scripted Components Part I](https://youtu.be/vJLfuVwbvGE)
- Video (spanish): [Creando componentes script en SimulIDE](https://www.youtube.com/watch?v=xRF0TBUU0JY)
- [Scripted Dev](../../../../4-Dev/Scripted%20Dev).

---

#tutorial