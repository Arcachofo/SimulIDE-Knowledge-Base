This file describes which kind of component it is and the parts or modules it contains.  

Each type of modular component has it's own characteristics and can use certain types of modules, but as a general idea this is the structure:

## Root element:
The principal characteristics are defined in the root element.<br>
**The tag name can be anything you want**, typical names are: "mcu" for microcontrollers or "iou" meaning Input/Output Unit.<br> 

```xml
<mcu name="mega8" core="AVR" data="1120" prog="4096" eeprom="512"freq="16000000" >
</mcu>
```

The possible fields in the root element are:

- **name:** name of the component, just for reference, has no effect.
- **core:** core type, available cores are: AVR, Pic14, Pic14e, 8051, 6502, Z80, scripted.
- **data:** size of data memory.
- **prog:** size of program memory in PGM words.
- **progword:** size of PGM word in bytes.
- **eeprom:** size of ROM.
- **freq:** clock frequency.
- **inst_cycle:** number of clock cycles per instruction cycle.
- **cpu_cycle:** number of clock cycles per cpu cycle.

<br>

---

# Modules:

You can add different modules:

## Registers:

Basic structure:
```xml
  <regblock  name="" start="" end="" offset="">
    <register  name=""    addr="0x0003"  reset=""  mask="" bits=""/>
    <register  name=""    addr="0x0003"  reset=""  mask="" bits=""/>
    <register  name=""    addr="0x0003"  reset=""  mask="" bits=""/>
  </regblock>
```

### Field "regblock":
Represents a block of memory containing registers.<br>
These registers must fit inside the RAM size defined in the root element.<br>

- **name:** block name (not important)
- **start:** start address.
- **end:** end address (must be <= RAM end).
- **offset:** address offset (this value is added to register address)

### Field "register":
Represents a single register.<br>
Register address must fit between regblock start and end addresses.

- **name:** Register name.
- **addr:** Register address (Hexadecimal without offset).
- **reset:** reset value, 8 bit, default = "00000000"
- **mask:** write mask, 8 bit, default = "11111111"<br>
    Affects only operations with DataSpace::writeReg()<br>
    mask = 0 : doesn't mask value but is write protected.<br>
    else : bits marked as 0 are masked out off the value.<br>
- **bits:** list of bit names (separated by commas).
    A 0 represents no name.

Registers must be defined before peripherals and interrupts because these can use register or bit names.

## Data block:


## PGM block:


## Stack:

---

## Interrupts:

Basic structure:
```xml
  <interrupts enable="">
    <interrupt name="" enable="" flag="" priority="" vector="" clear="" />
    <interrupt name="" enable="" flag="" priority="" vector="" clear="" />
    <interrupt name="" enable="" flag="" priority="" vector="" clear="" />
  </interrupts>
```

### Field "interrupts"
Represents a group of interrupts.

- **enable:** name of bit to enable global interrupts.

### Field "interrupt"
Represents a single interrupt.

- **name:** Interrupt name.
- **enable:** name of bit to enable this interrupt.
- **flag:** name of bit for interrupt raised flag.
- **priority:** number representing interupt priority (bigger means higher priority).
- **vector:** Program Memory address to jump at interrupt execution.
- **clear:** how to clear interrupt flag.
    If empty, clear flag after interrupt execution (auto-clear).
    If clear="1" clear flag by writing 1 to interrupt flag.
    If clear="0" deactivate auto-clear.

---

## Peripherals:

### ROM:

### MCU Port:

### IO Port:

### Timer:

### OCM:

(AVR)

### CCP unit:

(PIC)

### MSSP unit:

(PIC)

### ADC:

### DAC:

### Comparator:

### Vref:

### USART:

### TWI:

### SPI:

### Watchdog:

### Sleep:

### Config words:

### Int Osc:


