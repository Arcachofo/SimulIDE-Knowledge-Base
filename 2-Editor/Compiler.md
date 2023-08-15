# Compilers

To be able to compile source files you need to link a compiler to the file by opening "Compiler Settings" in ![[settings.svg]] Settings menu.

Then select a compiler from the list and configure "Tool Path":

![[comp_settings.png]]
Some compilers are automatically selected depending on the extension.
<br>

## Adding Compilers:

If the compiler you want is not included in the list, you can add new compilers.

Compilers are defined in xml files located at:
SimulIDE_1.x.x/data/codeeditor/compilers/compilers
SimulIDE_1.x.x/data/codeeditor/compilers/assemblers

To add a compiler, just add an xml file in any of those folders.
Your compiler will be added to the list in Compiler Settings dialog.

In this xml file you define the type of compiler, build path, syntax associated, build steps, etc.

---

## File structure:

The structure of the xml file is like this:

```xml
<compiler name="anyName" type="xx" buildPath="somePath" syntax="f.syntax" >
    <step 
        command="executable"
        arguments=" arguments for executable"
        argsDebug=" arguments for executable in debug mode"
    />
    <step 
        command="executable2"
        arguments=" arguments for executable2"
        argsDebug=" arguments for executable2 in debug mode"
    />
</compiler>
```

First the compiler name, type and other characteristics are defined in the field "compiler".
Then you can add as many build steps as you want in fields "step".

---

## Field "compiler":

```xml
<compiler name="anyName" type="anyType" buildPath="somePath" syntax="syntaxFile" >
```

**name:** This name will appear in the compiler list in Compiler Settings dialog.

**type:** can define certain characteristics of the debugger.
You can encode some characteristics in 2 numbers at the end, for example: type="myType01"
The key is in the last 2 numeric digits: "01".
From left to right:

First digit "0*" language level:
Value can be 0 or 1: 0 for asm, 1 for high level

Second digit "*1" lst file type:
Value can be from 0 to 3:
- Bit 0: use ":" ?
        0 doesn't use ":" (gpasm ).
        1 uses ":" (avra, gavrasm)
- Bit 1: position of flash address (0 or 1)


**buildPath:** folder to be used as build path by the compiler.
You can use "substitutions", for example if the source file is: myfile.asm
And you define buildPath like this: buildPath="build_$fileName"
Then a folder with name build_myfile will be created and used as build path.

Note that you must use this path in your command arguments if needed  (see example below).

**syntax:** syntax file used for highlighting.
Syntax files are located at: SimulIDE_1.x.x/data/codeeditor/syntax/
You can add your custom syntax files in that folder and use in your compiler definitions.

---

## Build steps:

You can add as many build steps as you want.
Each step need to have at least a "command".

```xml
    <step 
        command="executable"
        arguments=" arguments for executable"
        argsDebug=" arguments for executable in debug mode"
    />
```

**command:** command to execute.
**arguments:** arguments to add to the command when compiling.
**argsDebug:** arguments to add to the command when compiling for debug.

---

**Substitutions:**
You can use some substitutions in your command arguments and other values.
For example $FilePath will be replaced with the actual path to the source file.

Let's say we have this source file: /home/user/myfile.asm
Then we can use these substitutions:

| Wildcard        | Example               |              Replaced with |
|-----------------|:---------------------:|---------------------------:|
| **\$filePath**  | /home/user/myfile.asm |        complete file path  |
| **\$fileDir**   | /home/user/           |        path to file folder |
| **\$fileName**  | myfile         |     file name (without extension) |
| **\$fileExt**   | .asm           |         file extension (with dot) |
| **\$buildPath** | - |               build path (defined in xml file) |
| **\$inclPath**  | - |      include path (defined in Settings Dialog) |
| **\$family**    | - |     device family (defined in Settings Dialog) |
| **\$device**    | - |       device model (defined i Settings Dialog) |

---

## Example:

This is the xml file for Avr gcc compiler:

```xml
<compiler name="Avrgcc" type="avrgcc" buildPath="build_$fileName" useDevice="true">
    <step 
        command="avr-gcc"
        arguments=" -mmcu=$device -Wall -g -Os -o $buildPath$fileName.elf $filePath"
        argsDebug=" -mmcu=$device -Wall -g -Og -o $buildPath$fileName.elf $filePath"
    />
    <step 
        command="avr-objcopy"
        arguments=" -j .text -j .data -O ihex $buildPath$fileName.elf $buildPath$fileName.hex"
    />
<compiler/>
```

---

# Resources:

## Videos:
- [New custom compilers: avr-gcc with and without Makefile](https://www.youtube.com/watch?v=BHAbOa2GAIs)
- [SDCC Compiler & Debugger](https://www.youtube.com/watch?v=tnMongIYvsA)

---

#tutorial