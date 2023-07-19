[[Component list]]
[[Linking Components]]

## Customizable Components:

There are 2 main types of components you can create in SimulIDE:

- [[Subcircuits]]
- [[Modular]]

What they have in common:
They use "Packages" as graphical representation in the circuit.

You need to add them to the component list. This is done in a xml file like this:
```xml
<itemlib>

    <itemset category="Mine/Subcircuits" type="Subcircuit" folder="mySubcircuits" >

        <item name="Subcircuit1" info="This is just an example" />
        <item name="Subcircuit2" info="This is another example" />

    </itemset>

    <itemset category="Mine/MCUs" type="MCU" folder="myMcus" >

        <item name="Mcu1" info="This is a third example"/>
        <item name="Mcu2" info="This is the last example"/>

    </itemset>

</itemlib>
```

---

## Made of Subcircuits:
![[Subcircuits]]


---

## Modular Components:
![[Modular]]
