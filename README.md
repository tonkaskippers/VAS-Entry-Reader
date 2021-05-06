# VAS Entry Reader
Work in progress, still converting from MagicBand Reader.
Use with Raspberry Pi to interface VAS devices to ticketing systems.  
Fork of https://github.com/foolishmortalbuilders/magicbandreader

#Basic wiring:
* Connect PIXEL LEDS to  DATA on GPIO-18 (pin 12), pixel GnD to GND (pin 6) and pixel positive to +5v (pin 2)
* Connect USB VAS reader
* Connect Speaker via HDMI connector (ONBOARD SPEAKER WILL NOT WORK DUE TO Pixel LEDS!)

# Installation

* Install Raspbian lite onto pi. BE SURE TO INSTALL THE LITE VERSION: https://www.raspberrypi.org/downloads/raspberry-pi-os/ 
* Add ssh file and wpa_supplicant.conf to boot partition for wireless SSH access or log directly into Pi
* sudo apt install git
* git clone https://github.com/foolishmortalbuilders/magicbandreader.git
* cd vasentryreader
* sudo sh install.sh  (this will take awhile)
* cp * /home/pi/.
* sudo reboot now
* log back into pi
* vi /home/pi/settings.conf. and edit the led counts for your build
* sudo vi /etc/rc.local
  * Before the exit 0 line add:
  * (cd /home/pi; sudo python3 magicband.py &)
* sudo reboot now

# Config

Set the ring_pixels and symbol_pixel counts to the correct value

# Troubleshooting

If the install fails, try running this command first:
sudo apt-get update



