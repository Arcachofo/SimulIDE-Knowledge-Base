Configurable transformer

---

## Properties:

Property: (default value)

- **Coupling Coefficient:** (0.99)
<br>
- **Base Inductance:** (1 H)
   Inductance used in Primary and Secondary.
<br>
- **Primary:** (1)
   Description of primary coils (see below).
<br>
- **Secondary:** (1)
   Description of secondary coils (see below).

---

# Description of coils:

Coils are described by values separated by "**:**" or "**,**"

Each value represents the inductance, for example 1 is one time the base inductance, 2 is two times the base inductance and so on.

A negative value changes the direction of the coil (represented by the dot)

Separator "**:**" is used to separate completely independent coils or group of coils.
Separator "**,**" is used to separate interconnected coils in a group of coils.

Some examples:

![trafo0](trafo0.png)
![trafo1](trafo1.png)
![trafo2](trafo2.png)
![trafo3](trafo3.png)

---

# Resources:

- Video: [Transformer SimulIDE dev.](https://www.youtube.com/watch?v=s5aSr4GfpiM)

---

#Component 