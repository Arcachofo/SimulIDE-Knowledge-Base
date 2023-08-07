## Description:

This component can be configured as Ram or Rom.
You must save the circuit to get data persistance.

You can watch Memory content:
Right-Click and select "Show Memory Table".

You can save memory data to a file and load from file.

---

## Properties:

Property: (default value)

- **Size:** (65536 bytes)
   Size in bytes.
<br>
- **Control Code:** (80)
   Device address.
<br>
- **I2C Frequency:** (100 KHz)
   It is better to be similar to I2C Master frequency, but not critical in most cases.
<br>
- **Persistent:** (no)
   Save data to circuit file.
   If yes it acts as a ROM.

---

#Component 