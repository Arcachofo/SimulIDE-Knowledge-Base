# Code Editor

This is a plain text editor with syntax highlighting, cut, copy, paste, undo, redo and basic auto-indentation.

It is possible to open multiple documents that will be arranged in movable tabs.
When a file is modified, an asterisk: * will appear in the tab besides the file name.

## Sections:
- [#Tool bar](#Tool%20bar)
- [#Text editor](#Text%20editor)
- [#Message Panel](#Message%20Panel)


## Related topics:
- [Compiler](Compiler)
- [Debugger](Debugger)

---

# Tool bar

![edit_toolbar](edit_toolbar.png)
<br>

At the top we find the tool bar with 5 sections (from left to right):

## Settings:
>  ![settings](settings.svg) **Settings:** open settings menu:
> > [#Editor settings](#Editor%20settings).
> > [Compiler](Compiler) settings.

## File actions:
 >  ![lastfiles](lastfiles.svg) **Recent files:** show a list of last files used.
 >  ![new](new.svg) **New:** create a new empty document.
 >  ![open](open.svg) **Open:** open a text file from disk.
 >  ![save](save.svg) **Save:** save active document to disk.
 >  ![saveas](saveas.svg) **Save as:** save active document with new name.

## Find-replace:
 >  ![find](find.svg) **Find Replace:** open [Find-replace](Find-replace) Dialog.

## Compiler actions.
 >  ![compile](compile.svg) **Compile:** compile the active document.
 >  ![upload](upload.svg) **Upload to Micro:** compile and upload to active microcontroller in the circuit.

## Debugger  actions.
 >  ![debug](debug.svg) **Debug:** starts [Debugger](Debugger).

---

# Text editor

In the middle, the text editor itself is the space where we can see an edit text files.

## Editor Settings

- **Font Size:** sets the font size ( also ctrl+ and ctrl- works) ( default 9).
- **Tab Size:** sets the tab size ( default 4 ).
- **Spaces Tab:** if true tabs will be spaces, if false they will be tabs ( default false ).
- **Show Spaces:** if true you will differentiate empty from actual spaces or tabs.
    You  will see tiny dots representing spaces
    and tiny arrows representing tabs (default false):

![show_spaces](show_spaces.png)

## Context menu:

Open the context menu by Right-clicking to: Undo, Redo, Cut, Copy, Paste, Remove or Reload document.

## Indentation:

To indent press Tab key.
To unindent use Shift + Tab key.
You can select a block of text and indent/unindent it.

New lines follow the indentation of previous line.

## Syntax highlighting:

Syntax highlighting depends on the file extension and/or compiler used.
There are some syntax already supported:
- 6502 asm.
- AVR asm.
- I51 asm.
- PIC14 asm.
- Z80 asm.
- C/C++.
- GcBasic.
- Javascript.
- Makefile.
- Intel Hex.
- Xml.

You can modify existing ones or add new syntax using the files at: SimulIDE/data/codeeditor/syntax/

---

# Message Panel

This panel below the Editor view shows messages from the Editor, Compiler and Debugger.

Errors will appear highlighted in yellow background and warnings in bold orange.

---

# Resources:

- Video: [SimulIDE1.0.0 basic use: Editor](https://www.youtube.com/watch?v=NRLeEmM2vkE)

---

#tutorial