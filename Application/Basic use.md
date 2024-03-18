
## Getting SimulIDE:

To get SimulIDE just download a version compatible with your Operating System from the [download page](https://simulide.com/p/downloads/). 

Extract the contents of the compressed file you downloaded (.zip or .tar.gz). <br>
The folder "SimulIDE_x.x.x" contains all necessary to run the program.<br>

You can copy this folder to whatever location you want keeping the internal structure as it is.<br>
**Don't move, edit or delete files** unless you know what you are doing.

## To run this application:

Executable is in SimulIDE_x.x.x folder, just double-click it or run from a terminal if you want to see some messages about SimulIDE execution.  

You don't need to install anything else.

---

## Graphical User Interface:

The GUI is divided into 3 main panels.<br>
**All panels are resizable and collapsable.**

![[gui-basic-use.png]]

### Left Panel:

In the left panel you will find 2 tabs:

- [[Component list]] to select components and add to the circuit.
- [[File explorer]] to browse your file system and open files in the circuit or editor.
  
### Central Panel:

This is where the action happens, here is the circuit, power on/off buttons, settings and information about the simulation.<br>

These are the main sections:<br>
- [[Circuit Tool bar]] at the top with actions and information about the simulation.<br>
- [[Circuit canvas]] in the middle,  here is where you create and simulate your circuits.<br>
- [[Info panel]] at the bottom left, with information about the simulation.<br>
- [[Message panel]]  at the bottom right, showing debug messages and errors.<br>
  
### Right Panel:

In the right panel is the [[Code Editor| Editor/Compiler/Debugger]].<br>
It also has its own [[Code Editor#Tool bar|Tool bar]] and [[Message panel]].

This is a text editor with basic coding and debugging functionalities where you can write or edit source code for the microcontrollers supported. <br>
You can also open any kind of files in this editor, including binary files.<br>
For example you can open and edit SimulIDE configuration files, circuit files, hex files, etc.
  
---

## Creating circuits:

To create a circuit, just grab components from the [[Component list]] and drop into the [[Circuit canvas]].<br>
Then click in a Pin to start a wire and click in another pin to end the wire.

You can zoom in/out with the mouse wheel and pan with left button.<br>
Right-click in the canvas to open the [[Circuit canvas#Context menu|Circuit context menu]].

---

## Simulating circuits:

When you complete your circuit, click the Power button:  ![[poweroff.png | 20]]  in the [[Circuit Tool bar|Tool bar]] to start or stop the simulation.

You can pause the simulation with the pause button: ![[pausesim.png | 20]]

---

## Resources:

- Video: [SimulIDE1.0.0 basic use: GUI](https://www.youtube.com/watch?v=_HFxBLZyu0Y)

---

