# Custom Components

There are 2 main types of components you can create in SimulIDE:

## [Subcircuits](1-Circuit/Components/Subcircuits.md):
These are just circuits hidden inside a package.
<br>

## [Modular](1-Circuit/Components/Modular%20Components/Modular.md):
These are components created by combining different modules already implemented.
There are 3 types of Modular Components:
- [MCUs](1-Circuit/Components/Modular%20Components/Microcontrollers/MCUs.md)
- [MPUs](1-Circuit/Components/Modular%20Components/2-Microprocessors/MPUs.md)
- [Scripted](1-Circuit/Components/Modular%20Components/Scripted/Scripted.md)
<br>

All These components use [Package](1-Circuit/Components/11-Other/Package.md)s as graphical representation in the circuit, and some specific files for each type of component.

Creating a custom component involves these steps:

1. [](1-Circuit/Components/11-Other/Package.md#Creating%20Package%20File|Creating%20Package%20File.)
2. Creating specific files (see each component type).
3. [#Creating component folder](#Creating%20component%20folder) with all files.
4. [#Add to component list.](#Add%20to%20component%20list.)
<br>

---

## Creating component folder

The simplest way to do this is using the component name for the folder and all files.

An example is 74 series:
74HC00 files are in a folder named 74HC00 inside "ICs" folder, and all files use the sane name:

ICs (folder)  
- 74HC00 (folder) 
    - 74HC00.sim1
    - 74HC00.package
    -  74HC00_LS.package  
<br>

Each type of component have other options that allow to reuse package or other files in different components (see each component type).

The component folder is usually located inside SimulIDE data folder, but this is not a must.
<br>

---

## Add to component list.

In order to get your custom components included in the component list you need to add an entry to one of the existing xml files or create a new one.
These files are located at: share/simulide/data  
Please have a look to any existing .xml file in data folder to get an idea.

The simplest method and common options is explained here, but each type of component can have other options (see each component type).

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

- **category** Is the Category name where all components in this set will be included.
    It can be an existing Category or a new one.
    It can address a subcategory: "Category/Subcategory" (Category must exist)

- **type** Is the type of component.
- **folder** (optional) is the folder containing all components in this **itemset**.
- **icon** (optional) is the icon used for all the components in this **itemset**.
    The icon file must be in: data/images/

  
**item** Represents a component to be added to a Category

- **name** Is the name that will be shown in the [Component list](1-Circuit/Components/Component%20list.md).
- **info** (optional) Extra information that will be shown besides Component name.
- **icon** (optional) is the icon used for this component.  The icon file must be in: data/images/


---

# Resources:


---

#tutorial 