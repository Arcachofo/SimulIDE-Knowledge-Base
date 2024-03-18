Open main settings dialog in [[Circuit Tool bar]].<br>
There are 3 tabs:

- [[#Application settings]].
- [[#Circuit settings]].
- [[#Simulation settings]].

---

## Application settings

<table width=100%> <tr>
<td width=50%>
These setting need an application restart.

- **Language:** select application language.<br>
- **Font:** select font type for the GUI.<br>
- **Font Scale:** application font scale, for example: 0.8=80%, 1.5=150%.<br>
- **User data folder:** Folder to [[File organization#User data folder|add custom components and configuration files]].
</td>
<td width=50%> ![[app_set.png]] </td>
</tr> </table>

---

## Circuit settings

<table width=100%> <tr>
<td width=50%>

- **Draw Grid:** show or hide grid.<br>
- **Show Scrollbar:** show or hide scroll bars.<br>
- **Animate:** [[Circuit animation|animate wire color and pin color and modes]].
- **Canvas Refresh:**  number of Canvas updates/redraws per second.<br>
- **Auto Backup:** save Circuit backup if there are changes. (0 to disable)
</td>
<td width=50%> ![[circ_set.png]] </td>
</tr> </table>

---

## Simulation settings

<table width=100%> <tr>
<td width=50%>

- **Speed %:** Target simulation speed in percentage of real time.<br>
- **Steps per Second:** Another way to set simulation speed.<br>
- **Max Iterations:**  Number of maximum iterations for Non Linear loop (0 for no limit).<br>
- **Reactive Step:** Represents one step during charge/discharge of reactive components.<br>
    It should be small enough for each specific case.<br>
    It is possible to set custom Reactive Step for individual reactive components.
- **Slope Steps:** Number of steps for Output Pins rising/falling edges (0 for disabled).
</td>
<td width=50%> ![[sim_set.png]] </td>
</tr> </table>

---

## Resources:

- Video (english): [Simulation settings SimulIDE 1.0.0](https://www.youtube.com/watch?v=ZckENDMfUvU)
- Video (spanish): [Configurar simulación SimulIDE 1.0.0](https://www.youtube.com/watch?v=E_PW88gCGPw)
