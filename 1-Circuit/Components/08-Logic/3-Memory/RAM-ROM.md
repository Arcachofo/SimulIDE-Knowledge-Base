Static RAM/ROM.<br>

This component can be configured as Ram or Rom by setting persistance property.<br>
You must save the circuit to get data persistance.<br>

To watch Memory content:<br>
Right-Click and select "Show Memory Table".<br>

You can also save memory data to a file and load from file:<br>
Right-Click and select "Load data" or "Save data".

---

## Properties:
Property: (default value)

### Main:
- **Address Size:** (8 Bits)<br>
   Number of bits of address bus.<br>
   This determines the capacity (words = 2^Address_Size)<br>

- **Data size:** (8)<br>
   Number of bits of data bus.<br>
   This determines the length of a memory word.<br>

- **Persistent:** (no)<br>
   Save data to circuit file.<br>
   If yes it acts as a ROM.<br>

- **Asynchronous:** (no)<br>
   If yes it will be active while selected.<br>
   If no only active in CS pin active edge.<br>

### Electric:
![[Logic Components#Inputs]]<br>
![[Logic Components#Outputs]]<br>
- **Tristate:** (yes)<br>
   If yes, creates an enable pin (active Low).<br>
   When disabled, output is high impedance.<br>
      
- **Open Drain:** (yes)<br>
   If yes, output act as an open drain:<br>
   It can sink but not source current.<br>
   
![[Logic Components#Timing]]<br>
