Logic Analyzer  has 8 channels identified with different colors for each channel.<br>
You can connect inputs to wires or enter a tunnel name in the corresponding box.<br>
Connecting the inputs and running the simulation you will see the wave forms:

![[la01.png]]

---

## Properties:

Opening the properties (double-click) you can configure:<br>
- **Screen Size X**: screen width when not expanded (default: 135).<br>
- **Screen Size Y:** screen height when not expanded (default: 135).<br>
- **Buffer Size:** number of samples retained in memory (default: 100000).

![[la00.png]]

We will have a look at the "Export" group of properties later.

---

## Expanded mode:

Click in "Expand" button to get a window with a more detailed view and all the controls.<br>
This floating window is resizable and you can close it like any other window:

![[la02.png]]

---

## Controls:

From top to bottom, you can find the following controls:

## Time controls:
With these you can zoom-in or zoom-out in time (for all channels) and set the horizontal position of each channel.<br>
- **Time Div:** size of one horizontal division in the screen.<br>
- **Time Pos:** relative position in time.<br>
You can edit time values with the dial, or set a value in the correspondig box.<br>
You can enter a multiplier after the value in value boxes, for example write: "10m" + Enter, to set 10 miliseconds

**You can also use the mouse in Logic Analyzer screen:**<br>
- **Mouse wheel** to zoom in/out.<br>
- **Left-Click** and move to change position.<br>
- **Cursor** shows time value.

---

## Threshold:

Voltage used to detect logic states and triggers.<br>
- **↑**: **Low to High** threshold in Volts.<br>
- **↓**: **High to Low** threshold in Volts.<br>

---

## Trigger:
You can select any channel as a trigger source.<br>
Or you can select "Condition" trigger to pause simulation when a condition occurs.<br>
And enter an expression in the white box at the right.

**Condition trigger** works like a "one shot" trigger, but in addition it pauses the simulation, and you can zoom in/out, move in time, etc.<br>
Conditions are expressions like this:.<br>
**Ch1R** to pause in every channel 1 Rising egde.<br>
**Ch2F** to pause in every channel 2 Falling edge.

Available states are: **L, R, H, F**, for **L**ow, **R**ising, **H**igh, **F**alling.

You can use **logic expressions** like:<br>
( ( (Ch1R & Ch2H) | (Ch4L & Ch3H & Ch2F) ) & Ch6H ) | Ch8R

Conditions are case insensitive, Ch1R, cH1r or CH1r are valid.

---

## Export Data:
You can export the data in the screen by clicking this button.<br>
This will open a file dialog, to choose an **Vcd file** to save the data.

The "Export" tab in the properties dialog is related to this feature:

![[la03.png]]

- **Base Time Step:** time step used for the vcd file.
- **Export at pause:** automatically export vcd file at simulation pause (Condition Trigger).

You can combine Condition Trigger, Export Data and a program like [Pulseview](https://sigrok.org/wiki/PulseView) to do protocol decoding.

---

## Resources:

- Video (english): 
- Video (spanish): [Analizador Lógico SimulIDE 1.0.0](https://www.youtube.com/watch?v=NZvPPMa1Hfo)
