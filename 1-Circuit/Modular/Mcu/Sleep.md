AVR use 8 sleep modes defined by a register.
PIC use 1 sleep mode (just sleep or not sleep).


- Each McuModule has an uint8 sleepMode which indicates what to do when enter/exit sleep in each sleep mode.
  PICs only use 1/0 (sleep or not sleep)
  Timers that go to sleep must cancel events and re-schedule.

- Each interrupt has an uint8 wakeup flagset which enables/disables wakeup in each sleep mode.
  PICs don't use this, it will wakeup if module is running during sleep.
  
Sleep instruction calls eMcu::sleep( bool )
eMcu calls each McuModule:sleep( mode )

### TODO:
Determine sleep mode for each periferical.
And which functionality works during sleep.

Determine wakeups for each Interrupt in each device (Only AVR).
