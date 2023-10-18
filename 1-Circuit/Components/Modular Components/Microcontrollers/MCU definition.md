# MCU definition file


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
Represents a block of memory containing registers.

- **name:** block name (not important)
- **start:** start address.
- **end:** end address.
- **offset:** address offset (this value is added to register address)

### Field "register":
Represents a single register.

- **name:** Register name.
- **addr:** Register address (without offset).
- **reset:** reset value, 8 bit, default = "00000000"
- **mask:** 8 bit, default = "11111111"
    Affects only operations with DataSpace::writeReg()
    mask = 0 : doesn't mask value but is write protected.
    else : bits marked as 0 are masked out off the value.
- **bits:** list of bit names (separated by commas).
    A 0 represents no name.

Registers must be defined before peripherals and interrupts because these can use register or bit names.

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
- **priority:** number representing interupt priority (bigger has more priority).
- **vector:** Program Memory address to jump at interrupt execution.
- **clear:** how to clear interrupt flag.
    If empty clear flag after interrupt execution.
    If clear="1" clear flag by writing 1 to it.
    If clear="0" deactivate auto-clear.

---

## Peripherals:
