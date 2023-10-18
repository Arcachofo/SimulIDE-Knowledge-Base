# Compilers

Note that the compilers included in SimulIDE might not work in your system.
You probably need to change some setting in the xml file to meet the compiler installed in your system, for example executable name or extension (.exe for Windows). 
See [[#File Structure]] below.
If you have any questions please ask in our [forum](https://simulide.forumotion.com/)

Some compilers are automatically loaded for some file extensions, for example:
**.ino** : Arduino compiler.
**.gcb**: GcBasic compiler.
**.as** : Script compiler: 
If not, you need to set a compiler by opening "Compiler Settings" in ![[settings.svg]] Settings menu in the tool bar.
Then select a compiler from the list and configure "Tool Path" and other options (if needed):

![[comp_settings.png]]
To load a compiler automatically when you open a file, you can add an indication in the **very first line** of the file as a comment, for example in C/C++:

```
// Compiler: Avrgcc
```

Note that you must use the exact same name used in the compiler list.

## Compiling:

Once the compiler is configured you can compile the file by clicking in the compile button in the tool bar: ![[compile.svg]] 
Have a look at the bottom panel to see if there is some error.

If there are no errors you can upload the hex file generated to a microcontroller in the circuit by clicking the upload button in tool bar: ![[upload.svg]] 

Note that when there are more than one microcontroller in the circuit, the hex file will be uploaded to the "active" microcontroller, which is the one with a yellow dot:

![[mainmcu.png]]

To change the "active" microcontroller, right-click on it to open context menu and select "Main Mcu"
<br>

---

## Adding Compilers:

Compilers are defined in xml files located at:
SimulIDE_1.x.x/data/codeeditor/compilers/compilers
SimulIDE_1.x.x/data/codeeditor/compilers/assemblers

These xml files define the type of compiler, build path, build steps, syntax highlighting, etc.

If the compiler you want is not included in the list, you can add new compilers.

To add a compiler, just add an xml file in the folders mentioned above.
Your compiler will be added to the list in Compiler Settings dialog.
<br>

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
<br>

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
<br>

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
<br>

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
<br>

---

## Example:

This is a simplified version of the xml file for Avr gcc compiler:
```xml
<compiler name="Avrgcc" type="avrgcc" buildPath="build_$fileName" useDevice="true">
  <step 
    command="avr-gcc"
    arguments=" -mmcu=$device -Os -o $buildPath$fileName.elf $filePath"
    argsDebug=" -mmcu=$device -Og -o $buildPath$fileName.elf $filePath"
  />
  <step 
    command="avr-objcopy"
    arguments=" ihex $buildPath$fileName.elf $buildPath$fileName.hex"
  />
<compiler/>
```

Let's say that we are compiling a file with path: */path/toMyproject/mycode.c*
And we have these settings for the compiler:
**Tool Path:** */path/to/myCompiler/*
**Device:**  *atmega8*

It will do these substitutions for the first build step:

buildPath="build\_**$fileName**" is changed to: buildPath="/path/toMyproject/build_**mycode**"

-mmcu=**$device**  is changed to: -mmcu=**atmega8** 

**$buildPath** is changed to: **/path/toMyproject/build_mycode/**
**$fileName** is changed to: **mycode**
So **\$buildPath$fileName**.elf  becomes: **/path/toMyproject/build_mycode/mycode**.elf

**$filePath** is changed to: **/path/toMyproject/mycode.c**
<br>

In this case, because we indicated a buildPath, it will automatically create the build folder: 
*/path/toMyproject/build_mycode*

And the complete command it will execute for the first build step is this (all in one line):

```xml
"/path/to/myCompiler/avr-gcc" -mmcu=atmega8 -Os -o /path/toMyproject/build_mycode/mycode.elf "/path/toMyproject/mycode.c"
```
<br>

---

# Resources:

## Videos:
- [New custom compilers: avr-gcc with and without Makefile](https://www.youtube.com/watch?v=BHAbOa2GAIs)
- [SDCC Compiler & Debugger](https://www.youtube.com/watch?v=tnMongIYvsA)

---

#tutorial