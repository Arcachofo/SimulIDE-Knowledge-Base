There are also many of these in the default installation, for example Microcontrollers an Microprocessors.

There are 3 types of Modular Components:
- [[MCUs]]
- [[MPUs]]
- [[Scripted]]

These components are created from different "modules", for example: CPU, RAM, ROM, PGM, Ports, Timers, etc.

All these internal modules are defined in an xml file. There you describe the characteristics of the component and which modules to use and it's characteristics.

Creating a modular component involves at least 3 steps (Scripted needs an additional script file):

1. [[Package#Creating Package File|Creating Package File.]]
2. [[#Creating Definition file.]]
3. [[Custom Components#Add to component list|Add to component list.]]

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

---



---

#tutorial 