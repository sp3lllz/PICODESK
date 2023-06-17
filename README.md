# PICODESK

This is my open source hardware and software project to add memory function to IKEA motorised sit stand desks using the Resperry Pi Pico W

## WARNING! 

Doing this modification requires breaking open the opriginal controller in order to connect my board to the orgiginal doing this risks damaging your desk (I blew up a powersupply for the desk in protoyping this) and there is risk of personal injury. I bare no responsibility if this happens to you please do this modification at your own risk and always verify any hardware or software you use from this project before using them yourself. 

This project is designed to be fairly plug and play as well as low cost and invole minimal soldering, as a result i am using plug and play pi pico hats and mechanicial keyboard switches for the buttons. In the future I do plan on designing a more sleek version that some of the components intergrated more into the pcb such as the relays but that is a while off yet.

Here is what you will need for this project

Order the PCB from your PCB fabrication house of choice such as oshpark, JCLPCB or PCBway. Simply download the gerber zip file and upload it to their ordering system you shoudlnt need to chnage any settings but most might give you a pcb colour choice so go crazy!

Other components needed are:
Pi Pico W (Pi Pico will work for core functionality but at some point i plan to add a web interface for controll so pi pico w is reccomended) - https://www.raspberrypi.com/products/raspberry-pi-pico/?variant=raspberry-pi-pico-w

Waveshare Pico OLED 2.23 - https://thepihut.com/products/2-23-oled-display-module-for-raspberry-pi-pico 

SBC Dual Channel Relay HAT - https://thepihut.com/products/dual-channel-relay-hat-for-raspberry-pi-pico

Pimoroni TOF Sensor (functionality is WIP) - https://thepihut.com/products/vl53l1x-time-of-flight-tof-sensor-breakout

Pi Pico Legs (if you didnt order one with legs pre soldered) and Micro USB Cable - https://thepihut.com/products/essential-raspberry-pi-pico-kit

4 Cherry MX style Keycaps of your choice.

See assembly.md for futher instructions. https://github.com/sp3lllz/PICODESK/blob/main/assembly.md
