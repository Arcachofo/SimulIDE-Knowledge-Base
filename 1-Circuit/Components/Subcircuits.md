# Subcircuits

These components are just circuits "packed" inside a package.

There are already many subcircuits included in the default installation, for example all components of the 74 or CD series.
All the files for subcircuits in the default installation are in "data" folder.
You can have a look to the files of these components to get an idea of how they are implemented.

Creating a subcircuit involves 3 steps:

1. [[Package#Creating Package File|Creating Package File.]]
2. [[#Creating circuit file.]]
3. [[Custom Components#Add to component list|Add to component list.]]
<br>

---

# Creating circuit file.

To use a circuit in a subcircuit just connect your circuit to [[Tunnel]]s.
Then Set the names of these Tunnels the same as the **Pin Id**s in the Packages (not the Pin names).

Save this circuit and use this .sim1 file as circuit file.
  
You can do all in one Circuit, as in the image below, with both Chip and Logic Symbol packages and circuit.
This is not always required, but this way you can see and edit the package files and circuit in the same place:
  
![[subc4.png]]

---

# Resources:

## Videos:
- [Logic Subcircuits SimulIDE dev.](https://www.youtube.com/watch?v=NpuQUcKUbAg)

---

#tutorial 