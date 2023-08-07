## Description:

Simple configurable light emitting diode.

Blinks if maximum current is exceeded.

---

## Properties:

Property: (default value)

### Main:
- **Color:** (Yellow)
   Led color.
<br>
- **Grounded** (no)
   If yes, connect cathode to ground internally and hide cathode pin.
   Any wire already connected to cathode will be deleted.

### Electric:
- **Forward Voltage:** (2.4 V)
   Voltage drop when forward biased.
<br>
- **Max Current:** (0.03 A)
   Maximum current (it will blink if exceeded).
   Maximum brightness is reached at this current.
<br>
- **Resistance:** (0.6 Ω)
   Series resistance.

---

#Component 