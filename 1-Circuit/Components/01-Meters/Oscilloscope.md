Oscilloscope has 4 channels identified with different colors and frequency indicators for each channel.

There is one input pin per channel and one for reference voltage (last one besides Expand button).<br>
You can connect inputs to wires or enter a tunnel name in the corresponding box.<br>
Connecting the inputs and running the simulation you will see the wave forms:

![[osc-1.png]]

---

## Properties:
Property: (default value)

Opening the properties (double-click) you can configure:<br>
- **Screen Size X**: screen width when not expanded (default: 135).<br>
- **Screen Size Y:** screen height when not expanded (default: 135).<br>
- **Buffer Size:** number of samples retained in memory (default: 600000).

![[osc-0.png]]

---

## Expanded mode:

You can click in "Expand" button and get a window with a more detailed view and all the controls.<br>
This floating window is resizable and you can close it like any other window:

![[osc-3.png]]

---

## Controls:

From top to bottom, you can find the following controls:

### Channel Buttons:
With this row of buttons you can select the "active" channel.<br>
When you select a channel, value boxes will change to the channel color.<br>
Al changes done in **Time Pos**, **Volt Div** and **Volt Pos**, will be applied only to selected channel.<br>
To apply changes to all channels, click on "**All**" button.
![[osc-4.png]]

---

### Time controls:
With these you can zoom-in or zoom-out in time (for all channels) and set the horizontal position of each channel.<br>
- **Time Div:** size of one horizontal division in the screen.<br>
- **Time Pos:** relative position in time for selected channel.<br>

**You can also use the mouse in Oscilloscope screen:**<br>
- **Mouse wheel** to zoom in/out.<br>
- **Left-Click** and move to change position.<br>
- **Middle-Click** reposition time reference.<br>
- **Cursor** shows voltages for each channel and time value.

![[val.png]]

---

### Voltage controls:

To configure vertical size and position for each channel.<br>
- **Volt Div:** size of one vertical division in the screen.<br>
- **Volt Pos:** relative vertical position for selected channel.

You can edit time and voltage values with the dial, or set a value in the corresponding box.<br>
You can enter a multiplier after the value in value boxes, for example type: "**10m**" + **Enter**, to set 10 miliseconds or 10 miliVolts.

---

### Other controls:

**Filter:** Any voltage change below this value will not trigger.<br>
**Auto:** Auto-resize channel to fit in the screen.<br>
**Trigger:** Channel used to trigger.

**Hide:** hide channel from screen.

**Tracks:** Divide screen in different tracks:<br>
- **1** track: All channels will overlap in a single track.<br>
- **2** tracks: channels 1 and 3 in top track, 2 and 4 in bottom track.<br>
- **4** tracks: Each channel has it's own track.

![[track1.png]]

---

## Resources:

