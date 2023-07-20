Configurable electromagnetic relay.

Property: (default value)

Main:
- Normally Closed: (no)
   State with relay not active.

- Double Throw: (no)
   Yes: 2 throws per pole.
   No: 1 throw per pole.

- Poles: (1)
   Number of poles controlled by this relay.


Electric:
- IOn: (0.02 A)
   Minimun current that activates the relay.

- IOff: (0.01 A)
   Minimun current that holds the relay active.

Coil:
- Inductance: (0.1 H)
   Coil inductance.

- Resistance: (100 Ω)
   Coil resistance.

- Auto Step: (0 steps)
   Resize Reactive step automatically.
   The value sets the number of sub-steps.
   0 to disable.


#Component