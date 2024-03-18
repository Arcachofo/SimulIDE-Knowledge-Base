Reactive components are Capacitor and Inductor.<br>

These components are updated periodically by the simulator at a rate defined in **Reactive Step** in [[Settings#Simulation Settings|Simulation Settings]].

It is also possible to set a custom Reactive Step value for individual reactive components.

This value is 1 us by default, but you need to adjust it for specific cases.<br>
For example if a reactive component is part of an oscillating circuit, it's Reactive Step should be short enough to be as accurate as you want:<br>
If wave length is 100 ns and you want at least 50 "updates" during this period, then you need to set Reactive Step = 2 ns.<br>
But if you need less accuracy you could set it to 25 ns and only have 4 "updates" in that period.<br>

In some cases setting a proper Reactive Step is critical for the simulation to work correctly.<br>
For example consider this oscillator and see what happens with a proper Reactive step of 10 ns:<br>

![[reastep2.png]]
<br>
<br>
Now see how a Reactive step of 100 ns affects the accuracy of the charge/discharge curve and frequency:<br>

![[reastep1.png]]
<br>
<br>
And this is what happens if you use the default 1 us Reactive step:<br>

![[reastep0.png]]
<br>

Note that a shorter Reactive Step means more circuit recalculations and more cpu usage, and perhaps slower simulation speed.

