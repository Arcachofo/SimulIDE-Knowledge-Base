Configurable latch.

---

## Properties:
Property: (default value)

### Main:
- **Input Size:** (8 Channels)<br>
   Number of channels.<br>

- **Trigger Type:** (Enable)<br>
   "Clock" triggers every active edge.<br>
   "enable" any change during active state.<br>
   "None" hides Clock pin.<br>

- **Invert Outputs:** (no)<br>
   Invert output pins.<br>

### Electric:
![[Logic Components#Inputs]]<br>
![[Logic Components#Outputs]]<br>
- **Tristate:** (yes)<br>
   If yes, creates an enable pin (active Low).<br>
   When disabled, output is high impedance.<br>
      
- **Open Drain:** (no)<br>
   If yes, output act as an open drain:<br>
   It can sink but not source current.<br>
   
![[Logic Components#Timing]]<br>

