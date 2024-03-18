Configurable controlled source.

Feasible to make: **VCVS, CCVS, VCCS, CCCS**.

---

## Properties:
Property: (default value)

- **Current Source:** (true)<br>
   true: Current source.<br>
   false: Voltage source.<br>

- **Current Controlled:** (false)<br>
   true: Current controlled.<br>
   false: Voltage controlled.<br>
   Only active when controlled by Pins.<br>

- **Use Control Pins:** (true)<br>
   true: Variable Source controlled by Pins.<br>
   false: Fixed value Source or controlled by linker.<br>

- **Gain:** (1)<br>
   Gain respect to controlling value( current or voltage).<br>
   Only active when controlled by Pins.<br>

- **Current:** (1 A)<br>
   Fixed current value for current source.<br>
   Only active when not controlled by Pins.<br>

- **Voltage:** (5 V)<br>
   Fixed voltage value for voltage source.<br>
   Only active when not controlled by Pins.<br>

---