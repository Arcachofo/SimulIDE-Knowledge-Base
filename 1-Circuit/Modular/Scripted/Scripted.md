With Scripted Components it is possible to define the behaviour of the device in a script.

These components are defined in 3 files:
Component name = *comp_name* 

**Component file:** *comp_name*.mcu  
**Package file:** *comp_name*.package  
**Script file:** *comp_name*.as (defined in component file)
<br>

## Component file:
```xml
    <iou name="comp_name" core="scripted" script="comp_name.as" linkable="true" >

      <properties name="group name">
        <property name="prop1" type="double" />
        <property name="prop2" type="uint"   />
      </properties>

      <ioport name="PORTA" pins="A,B,C,D,E,F" />

    </iou>
```
linkable, properties and ioport (or other peripherals) are optional

**Script must implement property getters and setters:**
```c
    void setProp1( double val )
    double getProp1()
    void setProp2( uint val )
    uint getProp2()
```
<br>

## Script functions called from C++:
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
<br>

## Available C++ functions to call from the script:

```c
    void print( string &msg )
```

#### Component:
```c
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

    IoPort@  getPort( string port )
    IoPin@   getPin( string pin )
    McuPort@ getMcuPort( string port )
    McuPin@  getMcuPin( string pin )

    void INTERRUPT( uint vector )

    string getPropStr( int index, string name )
    void setLinkedValue( int index, int val, int i )
    void setLinkedString( int index, string val, int i )
```
#### IoPort@.
```c
    void setPinMode( uint mode )
    uint getInpState()
    void setOutState( uint state )
    void changeCallBack( eElement@ e, bool en )
```
#### IoPin@.
```c
    void setPinMode( uint mode )
    void setOutState( bool state )
    bool getInpState()
    double getVoltage()
    void setVoltage( double volt )
    void changeCallBack( eElement@ e, bool en )
```
#### McuPort@.
```c
    void controlPort( bool outCtrl, bool dirCtrl )
    void setDirection( uint dir )
    uint getInpState()
    void setOutState( uint state )
```
#### McuPin@.
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
<br>

# ScriptPerif:

### Peipheral interface for scripts.

**Mandatory functions to implement:**

Register C++ objects and functions:
```c
    void registerScript( ScriptCpu* cpu )
```
Register Script functions:
```c
    void startScript()
```


