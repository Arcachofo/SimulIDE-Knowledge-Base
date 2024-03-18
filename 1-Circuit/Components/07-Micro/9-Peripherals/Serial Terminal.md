Serial terminal is a component to send and receive data to any UART devices in the simulation.<br>

---

## Properties:

Property: (default value)

- **Baudrate:** (9600) <br>
   Transmission speed. <br>

- **Data Bits:** (8) <br>
   Number of data bits. <br>

- **Stop Bits:** (1) <br>
   Number of stop bits. <br>

---

## Use:

Connect Tx pin to other device Rx pin.<br>
And Rx pin to other device Tx pin:

![[serterm_use.png]]

Click **"Open" button to open the Serial Monitor** and see messages received or send your data.<br>

The serial monitor is divided in two panels:

- **Right panel:** shows the **data sent**.
- **Left panel:** shows the **data received**.

![[ser_term.png]]

There are "**Clear**" buttons for each panel at the bottom.<br>
To pause/ Resume logging data use the **Pause** button at the top left.

Use "**Send Text**" input box to send ascii characters.<br>
Activating the "**CR**" button will add a return character to the text.

Use "**Send Value**" input box to send 0-255 values.<br>

You can choose to print the data sent/received in different formats.<br>
Click in  the button at the top right side and choose from the list:

<table width=100%> <tr>
<td width=30%> ![[ser_print.png]] </td>
<td width=70%>

- **ASCII: ** Default.
- **HEX:** Hexadecimal (0x00)
- **DEC:** Decimal.
- **OCT:** Octal.
- **BIN:** Binary (8 bits).
</td>

</tr> </table>