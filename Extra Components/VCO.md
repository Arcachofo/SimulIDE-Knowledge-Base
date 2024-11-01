**Minimum version: 1.1.0-SR1.**<br>

Voltage Controlled Oscillator.<br>

Converts voltage to frequency: Volts to KHz<br>
Generating a configurable floating wave.<br>

![[vco.png]]

<br>
To use this Component,connect a voltage source to the Input pin.<br>
The wave will be present at the Output pins:<br>

![[vco_test.png]]

<br>

### Pins:
**- I:** Input pin.<br>
   Voltage to be converted to Frequency.<br>

**- Minus (-):**  pin for output wave.<br>
   Usually connected to Ground.<br>

**- Plus (+):** pin for output wave.<br>

<br>

## Properties:

### Main:
**- Multiplier:** (1)
...Relation between voltage and frequency.
   For example Multiplier = 0.1, 1 Volt -> 0.1 KHz

### Wave:
**- Wave type:** (Sine)
   Set output wave type.

**- Phase shift:** (0 º)
   Phase shift relative to wave start.

**- Quality: **(100)
   Number of steps per wave cycle.


### Electric:
**- Semi amplitude: **(2.5 V)
   Half wave amplitude. 

**- Middle Voltage:**  (0 V)
   Central voltage of the wave.
