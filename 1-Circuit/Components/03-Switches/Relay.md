Configurable electromagnetic relay.

---

## Properties:
Property: (default value)

### Main:
- **Normally Closed:** (no) <br>
   State with relay not active. <br>

- **Double Throw:** (no) <br>
   Yes: 2 throws per pole. <br>
   No: 1 throw per pole. <br>

- **Poles:** (1) <br>
   Number of poles controlled by this relay. <br>

### Electric:
- **IOn:** (0.02 A) <br>
   Minimun current that activates the relay. <br>

- **IOff:** (0.01 A) <br>
   Minimun current that holds the relay active. <br>

### Coil:
- **Inductance:** (0.1 H) <br>
   Coil inductance. <br>

- **Resistance:** (100 Ω) <br>
   Coil resistance. <br>

- **Reactive Step:** (0 steps) <br>
   Set custom Reactive step for this component. <br>
   This value overrides general [[Settings#Simulation Settings|Simulation Settings]]. <br>
   0 to use value set in [[Settings#Simulation Settings|Simulation Settings]]. <br>

---
