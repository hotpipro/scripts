**<h1>HotPi Pro - Mobile Hotspot & Media Server</h1>**

<br>

**<h3><ins>FEATURES</ins></h3>**

<br>

- **Wi-Fi Hotspot w/ Ethernet Bridge**

  - Simply connect to your Raspberry Pi via Wi-Fi or Ethernet using your smartphone, tablet, PC, or smart TV, and instantly gain access to your mobile internet connection, SMB file server, and DLNA media server.

- **Plug & Play Mobile Internet Connection**

  - Your mobile internet connection is automatically established when you plug your modem into a USB port as well as during system boot.

- **SMB File Server**

  - Easily access your file storage using a SMB-enabled device, such as a smartphone, tablet, or PC.

- **DLNA Media Server**

  - Easily access your media library using a DLNA-enabled device, such as a smart TV.

<br>

**<h3><ins>INSTALLATION INSTRUCTIONS</ins></h3>**

<br>

- Connect your Raspberry Pi to the internet.

- Download the script by entering the following command in the terminal:

**sudo wget -P /bin https://raw.githubusercontent.com/hotpipro/scripts/main/hotpipro**

- Edit your Wi-Fi country code, Wi-Fi network name, and Wi-Fi network password by entering the following command in the terminal:

**sudo nano /bin/hotpipro**

- Save your changes and exit the editor by pressing **CTRL+X**, then **Y**, then **ENTER** on your keyboard.

- Make the script executable by entering the following command in the terminal:

**sudo chmod 755 /bin/hotpipro**

- Install the script by entering the following command in the terminal:

**sudo hotpipro**

- Your Raspberry Pi will reboot and you are done.

<br>

**<h3><ins>USER COMMANDS</ins></h3>**

<br>
<br>

- START INTERNET CONNECTION

**hotpistart**

- STOP INTERNET CONNECTION

**hotpistop**

- LIST USB STORAGE

**hotpilist**

- MOUNT USB STORAGE

**hotpimount** \<**usb storage name**\>

example: **hotpimount sda1**

- UNMOUNT USB STORAGE

**hotpiunmount** \<**usb storage name**\>

example: **hotpiunmount sda1**

- READ-ONLY SMB SHARE

**hotpiread**

- WRITEABLE SMB SHARE

**hotpiwrite**

- RELOAD DLNA LIBRARY

**hotpireload**

- UPDATE RASPBERRY PI

**hotpiupdate**

<br>
<br>

**NOTE:** The script will run as is without any modifications; however, it is recommended to modify the "**country_code=**", "**ssid=**", and "**wpa_passphrase=**" parameters prior to installation, as the Wi-Fi country code is set to "**US**", the Wi-Fi network name is set to "**raspberrypi**", and the Wi-Fi network password is set to "**password**" by default. Please locate the "**# Wi-Fi Network**" section within the script. Your **Wi-Fi country code must be capitalized**, your **Wi-Fi network name must have 1-32 characters**, and your **Wi-Fi network password must have 8-63 characters**. Do **NOT** remove the apostrophe at the end of your Wi-Fi network password. Failure to follow these instructions correctly will result in your Wi-Fi access point not working or the script not installing properly.

<br>

**<h3><ins>EXAMPLE</ins></h3>**

<br>
<br>

\# Wi-Fi Network

<br>

echo 'interface=wlan0

bridge=br0

ieee80211n=1

hw_mode=g

channel=1

ht_capab=[HT40+]

wmm_enabled=1

wpa=2

wpa_key_mgmt=WPA-PSK

rsn_pairwise=CCMP

country_code=**UK**

ssid=**John's Wi-Fi**
 
wpa_passphrase=**1l0v3k1tt3ns**' > /etc/hostapd/hostapd.conf

<br>

**<h3><ins>Module Compatibility</ins></h3>**

<br>
<br>

HotPi Pro is set to run with the SIMCom SIM7600 module by default. Different modules may be used by modifying the vendor and product ID in the following line within the script prior to installation:

<br>

echo 'ATTR{idVendor}=="**1e0e**", ATTR{idProduct}=="**9001**", RUN="/bin/systemd-run hotpistart"' > /etc/udev/rules.d/hotpistart.rules

<br>

For example, to use the Quectel EC25 module, you would change **1e0e** to **2c7c** and **9001** to **0125** in the following manner:

<br>

echo 'ATTR{idVendor}=="**2c7c**", ATTR{idProduct}=="**0125**", RUN="/bin/systemd-run hotpistart"' > /etc/udev/rules.d/hotpistart.rules

<br>

Type **lsusb** in the terminal to get your specific module vendor and product ID. You should see something like this:

<br>

Bus 001 Device 009: ID 1e0e:9001 Qualcomm / Option SimTech, Incorporated

Bus 001 Device 003: ID 0424:ec00 Microchip Technology, Inc. (formerly SMSC) SMSC9512/9514 Fast Ethernet Adapter

Bus 001 Device 002: ID 0424:9514 Microchip Technology, Inc. (formerly SMSC) SMC9514 Hub

Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub

<br>

In this example, **Qualcomm / Option SimTech, Incorporated** is the SIMCom SIM7600 module and **1e0e:9001** is its vendor and product ID.
