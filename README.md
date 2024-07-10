# RaspberryPi_Note
First of all, you need a bootable SD card to install Raspberry Pi OS image.\
You may install Raspberry Pi OS using **Raspberry Pi Imager**:
```
# Get Raspberry Pi Imager from Raspberry Pi official site:
https://www.raspberrypi.com/software/
```
Please be noted, you should always erase your SD card first, then install Raspberry Pi OS.

## Enable UART login
After installing Raspberry Pi OS, connect the SD card to your workstation.\
Edit */boot/firmware/config.txt* in SD card to enable UART login.\
Add these lines:
```
# Disable BT and enable serial port
dtoverlay=pi3-miniuart-bt
core_freq=250
enable_uart=1
```
Save and exit.

## Show boot information from serial port
remove “quiet” in the line, save and exit.\
Check the serial port can be detected:
```
sudo dmesg | grep ttyUSB
```

## Use minicom to connect serial port
**minicom** can monitor serial ports.
```
# install minicom
sudo apt install minicom
# connect to serial port
sudo minicom -D /dev/ttyUSB0
```

