# UCTRONICS Ultimate Pi Rack OLED service
Simplified install process and aligned display fork for the UCTRONICS PoE Ultimate Pi Rack (U6143) OLED screens.

![rack_oled](https://user-images.githubusercontent.com/3183008/145669330-2cb575fe-fe35-405e-a50d-126c2f4b0be5.jpg)

## Changes
- Code-base: Removed unnessessary options, relying on CircuitPython module to keep setup quick and easy.
- Filenames: Changed filenames to more user-friendly text, i.e. `rack_oled.py` instead of `ssd1306_stats.py` 
- OLED Output: Fixed alignment and removed line overflows.

**Note**: I've only tested this on Raspberry Pi 4Bs running Ubuntu Server 20.04.

## Setup Process

- Grab this repo:
```bash
git clone https://github.com/MaxVRAM/pi_rack_oled.git
```

- Install required Python modules:
```bash
sudo apt install python3-pil
sudo pip3 install adafruit-circuitpython-ssd1306
```

- Test the script manually: 
```bash 
cd ~/pi_rack_oled
sudo python3 rack_oled.py
```

- If everything runs nicely, edit the provided service file to point to the script's location:
```bash
nano rack_oled.service
```

- Then link and add the service to your systemd:
```bash
sudo systemctl link /home/pi/pi_rack_oled/rack_oled.service
sudo systemctl enable rack_oled
sudo systemctl start rack_oled
```










