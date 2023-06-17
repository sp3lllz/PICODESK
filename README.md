# PICODESK

This is my open source hardware and software project to add memory function to IKEA motorised sit stand desks using the Resperry Pi Pico W

## WARNING! 

Doing this modification requires breaking open the opriginal controller in order to connect my board to the orgiginal doing this risks damaging your desk (I blew up a powersupply for the desk in protoyping this) and there is risk of personal injury. I bare no responsibility if this happens to you please do this modification at your own risk and always verify any hardware or software you use from this project before using them yourself. 

This project is designed to be fairly plug and play as well as low cost and invole minimal soldering, as a result i am using plug and play pi pico hats and mechanicial keyboard switches for the buttons. In the future I do plan on designing a more sleek version that some of the components intergrated more into the pcb such as the relays but that is a while off yet.

## Here is what you will need for this project

Order the PCB from your PCB fabrication house of choice such as oshpark, JCLPCB or PCBway. Simply download the gerber zip file and upload it to their ordering system you shoudlnt need to chnage any settings but most might give you a pcb colour choice so go crazy!

Other components needed are:
Pi Pico W (Pi Pico will work for core functionality but at some point i plan to add a web interface for controll so pi pico w is reccomended) - https://www.raspberrypi.com/products/raspberry-pi-pico/?variant=raspberry-pi-pico-w

Waveshare Pico OLED 2.23 - https://thepihut.com/products/2-23-oled-display-module-for-raspberry-pi-pico 

SBC Dual Channel Relay HAT - https://thepihut.com/products/dual-channel-relay-hat-for-raspberry-pi-pico

Pimoroni TOF Sensor (functionality is WIP) - https://thepihut.com/products/vl53l1x-time-of-flight-tof-sensor-breakout

Pi Pico Legs (if you didnt order one with legs pre soldered) and Micro USB Cable - https://thepihut.com/products/essential-raspberry-pi-pico-kit

4 Cherry MX style Keycaps of your choice.

See assembly.md for futher instructions. https://github.com/sp3lllz/PICODESK/blob/main/assembly.md

## Assembly Instructions

1. Start by flashing the latest MicroPython firmware onto your Raspberry Pi Pico. Visit the Raspberry Pi documentation page at https://datasheets.raspberrypi.com/ and download the firmware linked there. With the Pico unplugged, locate and press the small white button near the USB plug. While holding the button, plug the Pico into your laptop. A file explorer window/finder window will appear. Drag and drop the downloaded firmware folder into this window. After a few seconds, the window will disappear, indicating that the firmware has been flashed. You can now reconnect the Pico to reboot it.

2. Install Thonny from https://thonny.org/.

3. In the bottom right corner of the Thonny interface, you will find a selection box. Click on it and choose your Pi Pico from the list. The Pico should be listed as something like "COM2," indicating that it is connected via serial. Next, upload the "system_test.py" file to the Pico and rename it to "main.py" so that it runs automatically upon boot.

4. It's time to assemble the board. Place the Pi Pico and the relay HAT underneath the board, ensuring that the USB end faces the buttons' location. Insert the legs of the Pico through the corresponding holes on the board and solder them in place. Make sure the Pico legs provide enough length to connect the OLED screen to the Pico through the board. Connect the screen, paying attention to the orientation. Finally, add your preferred mechanical keyboard switches, i personally will be using Gateron Blues as they have a nice click to them which is perfect for this but if you want a more quieter use you can use liner or tactile instead. 

5. Power up the board. If you correctly renamed the "system_test.py" script to "main.py," it should automatically run the test. The test will display text on the screen, trigger the relays, and (work in progress) print the Time-of-Flight (TOF) distance. If everything is working, congratulations! You have set up the board correctly. Reconnect the Pi to your PC and replace the "main.py" file with the "picodesk.py" script, renaming it to "main.py." This will upload the desk control script to the Pi Pico, and the device should start functioning.

6. Disconnect your IKEA controller from your desk and remove the PCB from its plastic housing. The next step is tricky. Without removing the pads from the PCB, desolder the small plastic housing where the current button ribbon cable connects to the PCB. Solder three wires onto the corresponding pins. In the future, there are plans to create a ribbon connector for easy reversibility, but for now, this step is necessary.

7. Solder the wires to the three pads labeled "COM," "Up," and "Down" in the correct order. You can quickly test the functionality by using the up and down buttons on the left side of the board. These buttons provide manual control of the desk, bypassing the Pico controller board. This should make the desk move up and down as usual.

8. Plug in the Pi Pico and wait for it to boot. You should then be able to use the two buttons on the right side of the board to move the desk up and down to presets. Currently, the presets are based on the number of milliseconds it takes while the TOF sensor compatability is being developed in the future, a more precise method based on millimeters from the floor will be used. Stay tuned for updates.

9. To adjust the timing for sitting and standing, plug the Pi Pico into your computer and edit the variables for the timing in milliseconds. You can use the manual controls and a stopwatch on your phone to measure the desired timings.
