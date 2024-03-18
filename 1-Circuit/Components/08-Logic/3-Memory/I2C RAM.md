I2C RAM/ROM.

This component can be configured as Ram or Rom by setting persistance property.<br>
You must save the circuit to get data persistance.<br>

To watch Memory content:<br>
Right-Click and select "Show Memory Table".<br>

You can also save memory data to a file and load from file:<br>
Right-Click and select "Load data" or "Save data".

---

## Properties:
Property: (default value)

- **Size:** (65536 bytes)<br>
   Size in bytes.<br>

- **Control Code:** (80)<br>
   Device address.<br>

- **I2C Frequency:** (100 KHz)<br>
   It is better to be similar to I2C Master frequency, but not critical in most cases.<br>

- **Persistent:** (no)<br>
   Save data to circuit file.<br>
   If yes it acts as a ROM.<br>

---
