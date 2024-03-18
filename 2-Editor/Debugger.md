It is posible to debug many types of source codes in SimulIDE.<br>
For that, the proper [[Compiler]] should be configured and selected.

## Sections:
- [[#Starting debugger]]
- [[#Debugger actions]]
- [[#Breakpoints]]
- [[#Message Panel]]

## Related topics:
- [[Compiler]]
- [[Code Editor]]

---

## Starting debugger:

When your code can be compiled and uploaded without errors you can start a debugging session by clicking the debug button: ![[debug.svg]]

If everything is ok you will see a message similar to this at the bottom panel:

![[debug_msg.png]]

<br>
The tool bar will change to debugger mode and an arrow icon will point to the first line of code:

![[debug0.png]]

<br>

###  Debugger actions:
 > ![[step.svg]] **Step:** step to next line.<br>
 > ![[stepover.svg]] **Step Over:** step over function calls.<br>
 > ![[runtobk.png]] **Run to Breakpoint:** run until next breakpoint.<br>
 > ![[pause.svg]] **Pause:** pause if running.<br>
 > ![[reset.svg]] **Reset:** restart debugger.<br>
 > ![[stop.svg]] **Stop:** stop debugger.<br>

<br>
---

## Breakpoints:
You will notice that all lines that have been mapped are marked in dark green in the line number area:

![[debug_lines.png]]

These are the "active" lines, where the debugger will step and where you can place breakpoints.

You cann add or remove a breakpoints just by clicking in the line number area or by right-click and select action:

![[add_brk.png]]

<br>
Breakpoints appear as yellow squares in the line number area.<br>
And yellow indicators for all breakpoints will apeear in the scroll bar:

![[brk_scroll.png]]

<br>
---

##  Message Panel

This [[Message panel]] below the Editor view shows some information about the execution of each debugging step :<br>
- Source code line.
- Clock cycles that took to execute the step.
- Time that took to execute the step in microseconds.

![[debug_msg2.png]]

---
