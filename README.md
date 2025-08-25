**<h2>HotPi Pro - Mobile Hotspot & Media Server</h2>**

<br>

**<h3><ins>FEATURES</ins></h3>**

- **Wi-Fi Hotspot w/ Ethernet Bridge**

  -

- **Plug & Play Mobile Data Connection**

  - Your mobile data connection is automatically established when you plug your modem into a USB port as well as during system boot.

- **SMB File Server**

  -

- **DLNA Media Server**

  -

<BR>

**<h3><ins>SUPPORTED MODULES</ins></h3>**

- SIMCom SIM7600

- Quectel EC25

<br>

**<h3><ins>INSTALLATION INSTRUCTIONS</ins></h3>**

- Connect your Raspberry Pi to the internet.

- Download the script by entering the following command in the terminal:

**sudo wget -P /bin https://raw.githubusercontent.com/hotpipro/scripts/main/hotpipro**

- Edit your Wi-Fi country code, Wi-Fi network name, and Wi-Fi passphrase by entering the following command in the terminal:

**sudo nano /bin/hotpipro**

- Save your changes and exit the editor by pressing **CTRL+X**, then **Y**, then **ENTER** on your keyboard.

- Make the script executable by entering the following command in the terminal:

**sudo chmod 755 /bin/hotpipro**

- Install the script by entering the following command in the terminal:

**sudo hotpipro**

- Your Raspberry Pi will reboot and you are done.

<br>

**<h3><ins>USER COMMANDS</ins></h3>**

- START DATA CONNECTION

**hotpistart**

- STOP DATA CONNECTION

**hotpistop**

- MOUNT USB STORAGE

**hotpimount** \<**usb storage name**\>

example: **hotpimount sda1**

- UNMOUNT USB STORAGE

**hotpiunmount** \<**usb storage name**\>

example: **hotpiunmount sda1**

- RELOAD DLNA LIBRARY

**hotpireload**

<br>
<br>

**NOTE:** The script will run as is without any modifications; however, it is recommended to edit the "**country_code=**", "**ssid=**", and "**wpa_passphrase=**" parameters, as the Wi-Fi country code is set to "**US**", the Wi-Fi network name is set to "**RPI-5G**", and the Wi-Fi passphrase is set to "**passphrase**" by default. Please locate the "**# WI-FI NETWORK**" section within the script. Your **Wi-Fi country code must be capitalized**, your **Wi-Fi network name must have 1-32 characters**, and your **Wi-Fi passphrase must have 8-63 characters**. Do **NOT** remove the apostrophe at the end of your Wi-Fi passphrase. Failure to follow these instructions correctly will result in your Wi-Fi access point not working or the script not installing properly.
