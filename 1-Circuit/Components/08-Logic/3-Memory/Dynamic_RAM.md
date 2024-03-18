Dynamic RAM.<br>

To watch Memory content:<br>
Right-Click and select "Show Memory Table".<br>

You can also save memory data to a file and load from file:<br>
Right-Click and select "Load data" or "Save data".

---

## Properties:
Property: (default value)

### Main:
- **Row Address Size:** (8 Bits)<br>
   Number of bits of Rows of the Memory array.<br>
   This determines the total capacity (words = 2^Rows * 2^Columns)<br>

- **Column Address Size:** (8 Bits)<br>
   Number of bits of Columns of the Memory array..<br>
   This determines the total capacity (words = 2^Rows * 2^Columns)<br>

- **Data size:** (8)<br>
   Number of bits of data bus.<br>
   This determines the length of a memory word.<br>

- **Refresh period:** (0 ps)<br>
   Maximum time between Memory refreshes.<br>

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