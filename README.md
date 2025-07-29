# ssd1306-i2c-opi-python
Simple python code to display the i2c screen on Orange Pi

Check the C repo code here to know how to wiring, activate the i2c in orange pi system
https://github.com/thanhtantran/ssd1306-i2c-opi

This code is written by Anthropic Claude 4 and dipslay the CPU Usage, CPU Temp, RAM Usage and Local IP for development

This code initial written for Orange Pi CM5, so this is the i2c-5, if your board use different i2c location, change it in 
```
# Setup I2C interface for Orange Pi CM5
serial = i2c(port=5, address=0x3C)
```

Default address of i2c is `0x3C` after wiring and activating, you need to check and see it using `i2c-tools`
```bash
orangepi@orangepicm5-tablet:~$ sudo i2cdetect -y 5
[sudo] password for orangepi:
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:                         -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- 3c -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
70: -- -- -- -- -- -- -- --
orangepi@orangepicm5-tablet:~$
```

### 1. Install lib and dependencies
```
sudo apt install python3-pil
sudo pip3 install luma.oled luma.core psutil
```

### 2. Run the program
```
python oled_monitor.py
```
