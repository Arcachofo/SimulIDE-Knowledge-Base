## PIC: 
fuses based on PGM Address.

Fuses are contained in the hex file at special addresses.
These are detected by the loadHex algorythm.
Adress+value sent to PicConfigWord::setCfgWord which does the configuration:

- Oscillator type: Freq and Pins (McuIntOsc).
- Watchdog.
- Mclr Pin.
- Clock Out.


## AVR: 
fuses programmed directly.

Configuration is done in Component properties->Config.


#tutorial