# Optiboot-for-grbl
Atmega328P Bootloader for use with GRBL using spindle direction as spindle enable option.

Optiboot bootloader github: https://github.com/Optiboot/optiboot
GRBL github: https://github.com/gnea/grbl

Running grbl V0.9 and above you can use a complie time option " USE_SPINDLE_DIR_AS_ENABLE_PIN " to turn your router / spindle on and off via a relay using G-code ( M3 / M5 ) over the Arduino pin D13. This can have the effect of our router / spindle turning on and off every time the atmega328 starts up or resets due to Optiboot flashing the led that resides on arduino pin D13. Not a behavior we want in our cnc. To fix this we can run without a bootloader and burn grbl over icsp or update Optiboot to change this behavior. 

This is a repository for Optiboot 6.2 compiled using the following command to disable the flashing led on Arduino pin D13.
“make LED_START_FLASHES=0 atmega328”
