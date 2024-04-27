You can activate Circuit animation in [[Settings#Circuit settings|Circuit settings]].<br>

Circuit animation will colorize wires and pins to indicate logic states and characteristics of the pins.<br>

![[animate.png]]

---

## Wires:
Wire color represents logic states:<br>
- **Red:** High state (V > 2.5 V).<br>
- **Blue:** Low state (V < 2.5 V).<br>

Buses are always shown in green color with a thicker line.

---

## Pins:
Pin modes are represented by it's shape:<br>
The arrow indicates the direction and half arrow indicates open drain.<br>

Pin colors represent logic states as well, but different pin modes use different colors:<br>
Red, orange, green for High states and blues for Low states.<br>


| Undefined:             |  Input:            | Output:         | Output open drain:      |
|:------------------|:----------------|:----------------|:----------------------|
| <br>Active<br> ![[unac.png]]   | <br>Low<br> ![[inlo.png]]  | <br>Low<br> ![[oulo.png]] | <br>Driving Low<br>  ![[oplo.png]] |
| <br>Inactive<br> ![[undef.png]] | <br>High<br> ![[inhi.png]] | <br>High<br> ![[ouhi.png]] | <br>Floating Low<br> ![[opdlo.png]] |
|                             |                        |                        | <br>Floating High<br> ![[ophi.png]] |












