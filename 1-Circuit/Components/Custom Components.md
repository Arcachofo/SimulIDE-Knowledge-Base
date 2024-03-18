There are 2 main types of components you can create in SimulIDE:

## [[Subcircuits]]:
These are just circuits hidden inside a package.<br>
There is a [[Subcircuits|page specific for Subcircuits here]].


## [[Modular]]:
These are components created by combining different modules  that already implemented in SimulIDE.<br>
There are 3 main types of Modular Components:

- [[MCUs]]
- [[MPUs]]
- [[Scripted]]
<br>

All These components use [[Package]]s as graphical representation in the circuit, and some specific files for each type of component.<br>

Creating a custom component involves these steps:<br>

1. [[Package#Creating Package File|Creating Package File.]]
2. Creating specific files (see each component type).
3. [[#Creating component folder]] with all files.
4. [[#Add to component list.]]


---

## Creating component folder

The simplest way to do this is using the component name for the folder and all files.<br>

An example is 74 series:<br>
74HC00 files are in a folder named 74HC00 inside "ICs" folder, and all files use the sane name:<br>

ICs (folder)<br>
- 74HC00 (folder)<br>
    - 74HC00.sim1<br>
    - 74HC00.package<br>
    -  74HC00_LS.package<br>

Each type of component have other options that allow to reuse package or other files in different components (see each component type).<br>

The component folder is usually located inside SimulIDE data folder, but this is not a must.
<br>

---

## Add to component list.

In order to get your custom components included in the component list you need to add an entry to one of the existing xml files or create a new one.<br>

The xml files for components included in SimulIDE are located at: **Simulide/data/**  <br>
Please have a look to any existing .xml file in data folder to get an idea.<br>

You can add components in SimulIDE data folder, but those components will only be available for that installation of the program.<br>
If you want your components available for all versions/installations of SimulIDE then you should use the **"User data folder"** defined in [[Settings#Application settings|Application settings]].
In this folder you can add your custom components or override existing components with your own version.

The simplest method and common options is explained here, but each type of component can have other options (see each component type).<br>

The structure of these xml files is like this:  

```xml
<itemlib>  
  <itemset category="Some Category" type="Some_Type" folder="Some_Folder">  
	<item name="Name1" info="short explanation about Name1" />  
	<item name="Name2" info="short explanation about Name2" />  
  </itemset>
</itemlib>
```
  
Let's explain by levels:

**itemlib** Represents a library of components, with 1 or more sets of components.

**itemset** Represent a set of components in a Category.

- **category** Is the Category name where all components in this set will be included.<br>
    It can be an existing Category or a new one.<br>
    It can address a subcategory: "Category/Subcategory" (Category must exist)

- **type** Is the type of component.
- **folder** (optional) is the folder containing all components in this **itemset**.
- **icon** (optional) is the icon used for all the components in this **itemset**.<br>
    The icon file must be in: data/images/

  
**item** Represents a component to be added to a Category

- **name** Is the name that will be shown in the [[Component list]].
- **info** (optional) Extra information that will be shown besides Component name.
- **icon** (optional) is the icon used for this component.  The icon file must be in: data/images/

<br>

You can define specific folders for individual components, for that just add a field **folder** to that **item**:

  
```xml
<itemset category="Some Category" type="Subcircuit" folder="Some_Folder">  
  <item name="Name1" info="short explanation about Name1" />  
  <item name="Name2" info="short explanation about Name2" />  

  <item name="Comp_Y" folder="YY" info="My files in YY folder" />
  
</itemset>
```


---

## Resources:

---

#tutorial 