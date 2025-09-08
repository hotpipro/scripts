**<h1>HotPi Pro - Mobile Hotspot & Media Server</h1>**

<br>

**<h3><ins>FEATURES</ins></h3>**

<br>

- **Wi-Fi Hotspot w/ Ethernet Bridge**

  - Simply connect to your Raspberry Pi via Wi-Fi or Ethernet using your smartphone, tablet, PC, or smart TV, and instantly gain access to your mobile data connection, SMB file server, and DLNA media server.

- **Plug & Play Mobile Data Connection**

  - Your mobile data connection is automatically established when you plug your modem into a USB port as well as during system boot.

- **SMB File Server**

  -

- **DLNA Media Server**

  - Easily access your media library using your favourite DLNA-enabled device, such as a smart TV.

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

- RELOAD DLNA LIBRARY

**hotpireload**

<br>
<br>

**NOTE:** The script will run as is without any modifications; however, it is recommended to edit the "**country_code=**", "**ssid=**", and "**wpa_passphrase=**" parameters, as the Wi-Fi country code is set to "**US**", the Wi-Fi network name is set to "**raspberrypi**", and the Wi-Fi network password is set to "**password**" by default. Please locate the "**# Wi-Fi Network**" section within the script. Your **Wi-Fi country code must be capitalized**, your **Wi-Fi network name must have 1-32 characters**, and your **Wi-Fi network password must have 8-63 characters**. Do **NOT** remove the apostrophe at the end of your Wi-Fi network password. Failure to follow these instructions correctly will result in your Wi-Fi access point not working or the script not installing properly.

<br>

**<h3><ins>EXAMPLE</ins></h3>**

<br>
<br>

\# Wi-Fi Network

<br>

echo 'interface=wlan0

bridge=br0

ieee80211ac=1

channel=36

hw_mode=a

ht_capab=[HT40+]

wmm_enabled=1

wpa=2

wpa_key_mgmt=WPA-PSK

rsn_pairwise=CCMP

country_code=**UK**

ssid=**John's Wi-Fi**

wpa_passphrase=**1l0v3k1tt3ns**' > /etc/hostapd/hostapd.conf
