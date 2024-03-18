<table width=100%> <tr>
<td width=55%>
In the function component each output is defined by a mathematical expression that can take inputs states and voltages as well as previous output states.<br>

You can combine logic and analog values in a function.<br>

To edit functions click in the button next to each output pin.<br>
It will open a dialog to set the function. <br>
You can also edit the function in component properties. <br>

For example in a model of an OR gate with 2 inputs, the output function would look like this: <br>
    i0|i1
</td>
<td width=45%> ![[function.png]] </td>
</tr> </table>


## Logic operations:
  
- Not: **!**  
- And: **&**  
- Or:   **|**  
- Xor: **^**  
  
**Logic states:**  
- Input n:   "**in**"  
- Output n: "**on**"  
  
**Analog operations:**  
  
- Any mathematical operation aplicable to float numbers.  
  
**Voltages:**  
- Input n:   "**vin**"  
- Output n: "**von**"  
   
  
For example a model for a diferential amplifier with 2 inputs and 1 output, the output function would look like this (gain=10):  
    vo = (vi1-vi0)*10  
  
Note that to get output voltages instead of logis states, expression must start by "vo="  
  
You can combine logic and analog operations to get more complex behaivors.  
For exaple this expression...  
    vo = (vi1>vi0)*(vi1-vi0)+(vi1<=vi0)*vi0  
  
..Will do:  
- If Vi1 >Vi0: output = Vi1-Vi0  
- Else:           output = Vi0