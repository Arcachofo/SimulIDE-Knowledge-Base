# Modular Components

These components are created from different "modules", for example: CPU, RAM, ROM, PGM, Ports, Timers, etc.

All these internal modules are defined in an xml file. There you describe the characteristics of the component and which modules to use and it's characteristics.

There are 3 types of Modular Components:
- [MCUs](MCUs)
- [MPUs](MPUs)
- [Scripted](Scripted)

Creating a modular component involves at least these steps (Scripted needs an additional script file):

1. [](Package#Creating%20Package%20File|Creating%20Package%20File.)
2. [#Creating Definition file.](#Creating%20Definition%20file.)
3. [#Creating component folder](#Creating%20component%20folder) with all files.
4. [#Add to component list](#Add%20to%20component%20list)
<br>

---

# Creating Definition file.

This file describes which kind of component it is and the  parts or modules it contains.

Each type of modular component has it's own characteristics and can use certain types of modules, but as a general idea this is the structure:

This is an example of an definition file for an imaginary Microcontroller with 32 bytes of RAM, 256 of PGM, a group of Registers, one Port and one Timer:

```xml
<mcu name="Mcu1" core="Pic14" data="32" prog="256" progword="2" inst_cycle="4">

  <regblock name="SFR0" start="0x00" end="0x0B" >
  
    <register name="TMR0"   addr="0x01" bits=""/>
    
    <register name="OSCCAL" addr="0x05" reset="11111110"
              bits="FOSC4,CAL0,CAL1,CAL2,CAL3,CAL4,CAL5,CAL6"/>

    <register name="GPIO" addr="0x06" 
              bits="GP0,GP1,GP2,GP3"/>

    <register name="TRISGPIO" addr="0x07" bits="0-7" reset="00001111"/>

    <register name="OPTION" addr="0x08" reset="11111111"
              bits="PS0,PS1,PS2,PSA,T0SE,T0CS,GPPU,GPWU"/>
  </regblock>

  <port name="PORTP" pins="4" outreg="GPIO" dirreg="!TRISGPIO" 
                     inpmask="11110111" 
                     pullups="!GPPU" 
                     resetpin="PORTP3">
  </port>

  <timer name="TIMER0" type="800" configregsA="OPTION"
                       counter="TMR0"
                       clockpin="PORTP2"
  </timer>
```
<br>

---

## Creating component folder 

The simplest way is to use the the component name for the folder and all files as explained [](Custom%20Components#Creating%20component%20folder|here).

But it is possible to use different file names or use packages from other components.
To do this, you need to specify paths for these files as explained below.
<br>

---

## Add to component list.

The simplest method and common options is explained [](Custom%20Components#Add%20to%20component%20list|here).

But is is possible to use specific paths for package and definition files.
Path to all files are relative to "data" folder.

```xml
<itemlib>  
  <itemset category="Some Category" type="MCU">  
	<item name="Name1" package="file1.package" data="fileX.mcu" />  
	<item name="Name2" package="file2.package" data="fileY.mcu" />  
  </itemset>
</itemlib>
```
  
- **package** Is the path to package file, relative to SimulIDE data folder.  
- **data** Is the path to definition file, relative to SimulIDE data folder.
<br>

---

# Resources:

---

#tutorial 