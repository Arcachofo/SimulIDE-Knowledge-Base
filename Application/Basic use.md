## To run this application:

Just download a version compatible with your Operating System.  

Extract the contents of the compressed file you downloaded (.zip or .tar.gz).  
The folder "SimulIDE_x.x.x" contains all necessary to run the program. 
Executable is in this folder, just double-click it or run from a terminal if you want to see some messages about SimulIDE execution.  
  
You can copy this folder to whatever location you want keeping the internal structure as it is.  
**Don't move, edit or delete files** unless you know what you are doing.

You don't need to install anything else unless you are compiling yourself. Then you need to install [[Dependecies| these dependencies]].

---

# Graphical User Interface:

It is divided into 3 main panels.
**All panels are resizable and collapsable.**

![](gui-basic-use.png)

## Left Panel:

In the left panel therea are 2 tabs:
- [[Component list]] to select components and add to the circuit.
- [[File explorer]] to browse your file system and open files in the circuit or editor.  
  
## Central Panel:

- [[Circuit Tool bar]] at the top with actions and information about the simulation.
- [[Circuit canvas]] in the middle,  here is where you create and simulate your circuits.
- [[Message panel]]  at the bottom, showing debug messages and errors.
  
## Right Panel:

In the right pane is the [[Code Editor | Editor/Compiler/Debugger]].
It also has its own [[Code Editor#Tool bar|Tool bar]] and [[Code Editor#Message Panel|Message panel]].
This is a text editor with basic coding and debugging functionalities. 
  
---

# Creating circuits:

To create a circuit, just grab components from the [[Component list]] and drop into the [[Circuit canvas]].
Then click in a Pin to start a wire and click in another pin to end the wire.

You can zoom in/out with the mouse wheel and pan with left button.
Right-click in the canvas to open the [[Circuit context menu]].

---

# Simulating circuits:

When you complete your circuit, click the Power button:  ![[poweroff.png | 20]]  in the [[Circuit Tool bar | Tool bar]] to start or stop the simulation.

You can pause the simulation with the pause button: ![[pausesim.png | 20]]

---

# Resources:

- Video: [SimulIDE1.0.0 basic use: GUI](https://www.youtube.com/watch?v=_HFxBLZyu0Y)

---

#tutorial