## Description:

This component can be configured as Ram or Rom.
You must save the circuit to get data persistance.

You can watch Memory content:
Right-Click and select "Show Memory Table".

You can save memory data to a file and load from file.

---

## Properties:

Property: (default value)

### Main:
- **Address Size:** (8 Bits)
   Number of bits of address bus.
   This determines the capacity (words = 2^Address_Size)
<br>
- **Data size:** (8)
   Number of bits of data bus.
   This determines the length of a memory word.
<br>
- **Persistent:** (no)
   Save data to circuit file.
   If yes it acts as a ROM.
<br>
- **Invert Outputs:** (no)
   Invert output pins.
<br>
- **Asynchronous:** (no)
   If yes it will be active while selected.
   If no only active in CS pin active edge.

### Electric:
![[Logic Components#Inputs]]
![[Logic Components#Outputs]]
![[Logic Components#Edges]]

#Component 