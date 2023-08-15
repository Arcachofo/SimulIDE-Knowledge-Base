There are 2 main types of components you can create in SimulIDE:

- [[Subcircuits]]
- [[Modular]]

What they have in common:
- They use [[Package]]s as graphical representation in the circuit.
- You need to add them to the component list (Add entry to .xml file). 

---

## Add to component list.

In order to get your subcircuit included in SimulIDE component list you need to add an entry to one of the existing xml files or create a new one.
These files are located at: share/simulide/data  
Please have a look to any existing .xml file in data folder to get an idea.
  
The structure of these xml files is like this:  

```xml
<itemlib>  
  <itemset category="Some Category" type="Subcircuit">  
	<item name="Name1" package="file1.package" subcircuit="file1.sim1" />  
	<item name="Name2" package="file2.package" subcircuit="file2.sim1" />  
  </itemset>
</itemlib>
```
  
 Let's explain by levels:

**itemlib** Represents a library of components, with 1 or more sets of components.

**itemset** Represent a set of components in a Category.

- **category** Is the Category name where all components in this set will be included.
    It can be an existing Category or a new one.
    It can address a subcategory: "Category/Subcategory" (Category must exist)

- **type** Is the type of component, in this case it is always "Subcircuit"

  
**item** Represents a component to be added to the list

- **name** Is the name that will be shown in Component list
- **package** Is the path to package file, relative to data folder (where the .xml file is located).  
-  **subcircuit** Is the path to subcircuit file, relative to data folder (where the .xml file is located).
- **info** (optional) Extra information that will be shown besides Component name.
    
There is an option to simplify these entries by indicating the folder where subcircuit and package files are located.
For this option to work, all names must be the same, and files must be in a folder with same name.
 
An example is 74 series:
74HC00 files are in a folder named 74HC00 inside "ICs" folder.

ICs (folder)  
- 74HC00 (folder) 
    - 74HC00.sim1
    - 74HC00.package
    -  74HC00_LS.package  
  
Then the xml file entry looks like this:

```xml
    <itemset category="IC 74/7400-7499" type="Subcircuit" folder="ICs">  
        <item name="74HC00"  info="quad 2-input NAND gate" ></item> 
```
  
In this case, **folder** attribute is applied to all components in that **itemset**.

But it is possible to use a different one for each **item**.

Or set the exact path for **package** and **subcircuit** files:
  
```xml
<itemset category="IC 74/7400-7499" type="Subcircuit" folder="ICs">  

  <item name="74HC00"  info="  quad 2-input NAND gate" />

  <item name="Comp_X" folder="XX" info=" My files in XX folder" />
  
  <item name="Comp_Y" package="blah/cY.package" subcircuit="bla2/compY.sim1" 
                      info=" My files in blah & bla2 folders" >
  </item>
  
</itemset>
```

Subcircuit and package files are usually located in folders inside data folder, but this is not a must.
Path to these files are relative to "data" folder.
