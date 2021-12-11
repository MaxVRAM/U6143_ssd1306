# UCTRONICS Ultimate Pi Rack OLED service
This is a modified setup process to the original supplied by UCTRONICS to install the OLED service for their PoE Ultimate Pi Rack (U6143).
After attempting several other options they provided that require building C programs that had missing dependencies, I found the Python approach to be easiest.

Note: I'm using this on Raspberry Pi 4Bs running Ubuntu Server 20.04. 

## Setup Process

- Grab this repo:
```bash
git clone https://github.com/MaxVRAM/pi_rack_oled.git
```

- Install required Python modules:
```bash
sudo pip3 install adafruit-circuitpython-ssd1306
sudo apt-get install python3-pil
```

- Test the script manually: 
```bash 
cd ~/pi_rack_oled
sudo python3 rack_oled.py
```

- If everything runs nicely, add the service to your systemd:
```bash
sudo systemctl link /home/pi/pi_rack_oled/rack_oled.service
sudo systemctl enable rack_oled
sudo systemctl start rack_oled
```










