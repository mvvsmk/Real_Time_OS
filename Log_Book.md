# Log Book

This file contains all the things I will learn during this journey. The data provided here is present throughout my code as comments, as it is where I jot them down while coding. I will try to put them up on my Django blog site when it gets ready for deployment.

## Day 1

To start writing an RTOS, I'll need an IDE to make my life way less stressful. I go with AMD KIEL MDK (u vision), as it provides me the documentation of the ARM chipset. The documentation will come in handy when configuring the GPIO pins and seeing which register maps to which bus and all bits you need to flip to enable said pins.

I couldn't find a better alternative in Linux(Manjaro); hence, I would have to shift to windows for this project.

### Steps to configure the GPIO pins
1) Enable clock access to the Port of the Pins
1) Set the PIN's mode
1) Set output (we are going to set up the four led to the output pins)

According to the documentation, the onboard LEDs connect to the GPIO pin D, which in turn connect to the `AHB1` bus, and we can set it as enabled by using/giving 1 to bit 3 of the `AHB2_EN` register

for some reason, ST decided to remove the schematic for the board, but I managed to figure it out this is all the Pins on the Port D
* PD12- green
* PD13- orange
* PD14- red
* PD15- blue

I will try to develop a complete board support package that should automate this.
