(This feature is not available in version 1.0.0)<br>

Scripted components are a type of [[Modular]] Components, with an extra file containing a script to define the behaviour of the device.<br>

Creating an Scripted component involves these steps:

1. [[Package#Creating Package File|Creating Package File.]]
2. Creating [[Definition file]].
3. [[#Creating Script file.]]
4. [[#Creating component folder]] with all files.
5. [[Modular#Add to component list|Add to component list.]]

---

#  Creating [[Definition file]].

This are xml files describing which kind of component it is and the  parts or modules it contains.<br>

## Root element:
The principal characteristics are defined in the root element.<br>
**The tag name can be anything you want**, typical names are: "mcu" for microcontrollers or "iou" meaning Input/Output Unit.<br> 
Possible fields in the root element are the same for all  [[Modular]] Components

```xml
    <iou name="comp_name" core="scripted" script="file.as" >
    </iou>
```

We can see that **core**  is set to *"scripted"* , so this is an Scripted  component, and the **script** is in *"file.as"* .<br>

These are some modules and features you can add to a Scripted Component:


## Properties:

You can add properties to configure some settings in your component.<br>

```xml
    <iou name="comp_name" core="scripted" script="file.as" >

      <propertygroup name="group name">
        <property name="Prop1" type="double" />
        <property name="Prop2" type="uint"   />
      </propertygroup>

    </iou>
```

We can see that there is a property group with 2 properties.<br>
The property group has a field **name**,  this is the name shown in the property dialog.<br>

Each property has 2 fields:

- **name:** property name.
- **type:** data type ( bool, double, int, uint, string ).

**The script must implement property getters and setters:**

```c
    void setProp1( double val )
    double getProp1()
    void setProp2( uint val )
    uint getProp2()
```

These getters and setters are called from the [[ Properties dialog]] in the GUI.<br>
Typically the script has a variable to hold the property value.

When the setter is called, the script can apply any constrains to the value (like maximum or minimum value) and store it in that variable.

When the getter is called, the script typically returns the value of that variable.
<br>

---

## IO Ports:

### Definition file:

```xml
    <iou name="comp_name" core="scripted" script="file.as" >

      <ioport name="PORTA" pins="A,B,C,D,E,F" />

    </iou>
```

Each port has 2 fields:

- **name:** property name.
- **pins:** list of pin names separated by commas.

<br>

---

## Communications:

You can add some modules for communications.<br>

### UART:

```xml
    <iou name="comp_name" core="scripted" script="file.as" >

      <uart/>

    </iou>
```


### SPI:

```xml
    <iou name="comp_name" core="scripted" script="file.as" >

      <spi/>

    </iou>
```


### TWI:

```xml
    <iou name="comp_name" core="scripted" script="file.as" >

      <twi/>

    </iou>
```

<br>

---

## Display:


<br>

---

## Console:

<br>



---

# Creating Script file.

This is a program written in [[#The script language]] describing the behavior of the component.<br>

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

### Debug messages:

```c
    void print( string &msg )
```

<br>

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

// For linked Components:
// index: index on Linked component in the list
    string getPropStr( int index, string name )
    void setLinkedValue( int index, int val, int i )
    void setLinkedString( int index, string val, int i )
```

<br>

### IoPort@

```c
    void setPinMode( uint mode )
    uint getInpState()
    void scheduleState( uint32 state, uint64 time )
    void setOutState( uint state )
    void changeCallBack( eElement@ e, bool en )
    void addSequence( array<array<uint64>>@ t )
    void trigger( uint n ) // Trgger sequence
```

<br>

### IoPin@.

```c
    void setPinMode( uint mode )
    void setOutState( bool state )
    void scheduleState( bool state, uint64 time )
    void setStateZ( bool z )
    bool getInpState()
    double getVoltage()
    void setVoltage( double volt )
    void setOutHighV( double volt )
    void setImpedance( double imp )
    void changeCallBack( eElement@ e, bool en )
    bool isConnected()
```

<br>

### McuPort@.

```c
    void controlPort( bool outCtrl, bool dirCtrl )
    void setDirection( uint dir )
    uint getInpState()
    void setOutState( uint state )
```

<br>

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

<br>

---
# The script language

https://www.angelcode.com/angelscript/sdk/docs/manual/doc_script.html

## Arrays:

https://www.angelcode.com/angelscript/sdk/docs/manual/doc_datatypes_arrays.html

```c
// A zero-length array of integers
  int[] a;
  array<int> a;
  
// An array of integers with 3 elements
  int[] b(3);
  array<int> b(3);

// An array of integers with 3 elements, all set to 1 by default
  int[] c(3, 1);
  array<int> c(3, 1);
  
// An array of integers with 3 elements with specific values
  int[] d = {5,6,7};
  array<int> d = {5,6,7};

// An empty array of arrays of integers
  int[][] a;
  array<array<int>> a;

// A 2 by 2 array with initialized values
  int[][] b =  {{1,2},{3,4}};
  array<array<int>> b = {{1,2},{3,4}};

// A 10 by 10 array of integers with uninitialized values
  int[][] c(10, int[](10));
  array<array<int>> c(10, array<int>(10));
  
```




---

# Resources:

- [Forum discussion,](https://simulide.forumotion.com/t990-scripted-components)
- Video (english): [Creating Scripted Components Part I](https://youtu.be/vJLfuVwbvGE)
- Video (spanish): [Creando componentes script en SimulIDE](https://www.youtube.com/watch?v=xRF0TBUU0JY)
- [[Scripted Dev]].

---

#tutorial