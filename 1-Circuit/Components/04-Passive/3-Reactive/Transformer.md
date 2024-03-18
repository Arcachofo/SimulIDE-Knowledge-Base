Configurable transformer.

This transformer is highly configurable, allowing users to set up as many coils as needed on each side.<br>
It's even possible to use coils exclusively on one side.

The term "Primary" refers to the left side, while "Secondary" refers to the right side.<br>
However, any coil can function as the primary coil within the transformer.

---

## Properties:
Property: (default value)

- **Coupling Coefficient:** (0.99) <br>

- **Base Inductance:** (1 H) <br>
   Base inductance for all coils (refer to the coil descriptions below) <br>

- **Primary:** (1) <br>
   Description of coils in the left side (refer to the coil descriptions below). <br>

- **Secondary:** (1) <br>
   Description of coils at the right side (refer to the coil descriptions below). <br>

---

## Description of coils:

Coils are defined by values separated by "**:**" or "**,**" <br>
Separator "**:**" separates independent coils or groups of coils.<br>
Separator "**,**" separates interconnected coils within a group. <br>

Each value represents the voltage relation for one coil.<br>
For example, using 1 for the primary coil and 2 for the secondary coil results in a 2x voltage at the secondary. <br>
Or 1 for the primary coil and 0.5  for the secondary coil results in half the voltage at the secondary. <br>

A negative value changes the direction of the coil (identified by the dot). <br>

The coil inductance is calculated as follows:<br>
Coil inductance = Base Inductance x value x value.

For instance, with a Base Inductance of 10 H and coils with values 1 and 3, the inductances will be:<br>
Coil-1: L1 = 10 x 1 x 1 = 10 H<br>
Coil-2: L2 = 10 x 3 x 3 = 90 H<br>

You can use the number of turns for these values.<br>
To do this you need to know the number of turns and Inductance of one of the coils, usually the primary coil. And use this formula:

Base Inductance =  L / N^2

Where L is the inductance of that coil and N the number of turns.

---

Some examples:

![[trafo0.png]]
![[trafo1.png]]
![[trafo2.png]]
![[trafo3.png]]

---

## Resources:

- Video: [Transformer SimulIDE dev.](https://www.youtube.com/watch?v=s5aSr4GfpiM)

---
