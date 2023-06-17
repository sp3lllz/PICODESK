Here is what you will need for this project

Order the PCB from your PCB fabrication house of choice such as oshpark, JCLPCB or PCBway. Simply download the gerber zip file and upload it to their ordering system you shoudlnt need to chnage any settings but most might give you a pcb colour choice so go crazy!

Other components needed are:
Pi Pico W (Pi Pico will work for core functionality but at some point i plan to add a web interface for controll so pi pico w is reccomended) - https://www.raspberrypi.com/products/raspberry-pi-pico/?variant=raspberry-pi-pico-w

Waveshare Pico OLED 2.23 - https://thepihut.com/products/2-23-oled-display-module-for-raspberry-pi-pico 

SBC Dual Channel Relay HAT - https://thepihut.com/products/dual-channel-relay-hat-for-raspberry-pi-pico

Pimoroni TOF Sensor (functionality is WIP) - https://thepihut.com/products/vl53l1x-time-of-flight-tof-sensor-breakout

Pi Pico Legs (if you didnt order one with legs pre soldered) and Micro USB Cable - https://thepihut.com/products/essential-raspberry-pi-pico-kit

4 Cherry MX style Keycaps of your choice.

Next you need to flash your pico with the latest micropython firmware that is linked on the pi documentation page https://datasheets.raspberrypi.com/
to do this with the pico unplugged press and hold the small white button near the usb plug and while holding it plug the pico into your laptop. 
A file explorer window/finder window will pop up simply drag and drop the firmware folder you just downloaded into this window and within a few seconds it will disapear.
The pi will now flash the firmware this usually takes a few seconds then you can replug the pi to make it reboot. 

Now you will need thonny https://thonny.org/

in the bottom right corner you should see a selection box click this and choose your pi pico from the list, it should say somthing like COM2 this just means that it is connected via serial next upload the system_test.py file to the pico and rename it to main.py so that it will run upon first boot. 

Now its time to assemble the board, the pi pico and the relay hat go on the underneith of the board with the usb end facing toward where the buttons are located put the legs through the holes and solder them into place, make sure there is enough length on the pico legs that you will be able ot plug the OLED screen into the picos legs through the board then connect the screen paying attention to orientation. finally add your mechanicial keyboard switches of your choice all types of cherry sytle switches i will be using Gateron Blues due to their low cost and clickyness but your welcome to use linar or tacticle switches instead if youd like. 

now power up the board, providing you renamed the system test python script to main.py it should begin to auto run the test this will draw text to the screen fire the relays and (WIP) print the TOF distance (WIP) if everything is working congratualtions you set the board up correctly now connect the pi back to the pc and replace the main.py with the picodesk.py script renaming it to main.py this will upload the main script to the pi pico and the device shoudl begin to function. 

Now you will need to unplug your ikea controller from your desk and then remove the pcb from the plastic housing now comes the tricky part. now you will need to remove and desolder (without removing the pads from the pcb) the small plasic hosing where the current button ribbon cable connects to the pcb and soler on 3 wires to the pins that are used. In the future I plan on making a ribbon connector from my board to the ikea board so that the mod is fully reversable however for now this step is needed.

You will then need to solder the wires to the 3 pads labeled com up and down (in the right order) you can then quickly test functionality using the up and down button on the left side of the board these are the manual controls of the board that use the original functionallity of the ikea controller and bypass the pico controller board. this should meake the desk move up and down like normal. 

plugging in the pi pico and waiting for it to boot you should then be able to press the two butttons on the right side to move the desk up and down to presets, currently it is based on number of miliseconds it takes while the TOF sensor is WIP, once that is complete a more precise meothord of mm from the floor will be used instead, stay tuned. 

to adjust the timing for sitting and standing plug the pico into the computer and edit variable for the timeing in miliseconds you can use the manual controls and the stopwatch on your phone to measure this. 
