**<h3>Install HotPi Pro</h3>**

sudo wget -P /bin https://raw.githubusercontent.com/hotpipro/scripts/main/hotpipro

sudo chmod 755 /bin/hotpipro

sudo nano /bin/hotpipro

- wi-fi network country code, name, password

  - echo 'bridge=br0
  - channel=1
  - country_code=**US**
  - hw_mode=g
  - ieee80211n=1
  - interface=wlan0
  - rsn_pairwise=CCMP
  - ssid=**raspberrypi**
  - wmm_enabled=1
  - wpa=2
  - wpa_key_mgmt=WPA-PSK
  - wpa_passphrase=**password**' > /etc/hostapd/hostapd.conf

- cellular modem vendor ID, product ID

  - echo 'ATTR{idVendor}=="**1e0e**", ATTR{idProduct}=="**9001**", RUN="/bin/systemd-run hotpistart"' > /etc/udev/rules.d/hotpiauto.rules

CTRL+X, Y

sudo hotpipro

**<h3>Wi-Fi Network</h3>**

sudo nano /etc/hostapd/hostapd.conf

- Wi-Fi N 2.4 GHZ 72 Mbps (Raspberry Pi 3, 3B+, 4, 5)

  - channel=1
  - hw_mode=g
  - ieee80211n=1

- Wi-Fi AC 5 GHZ 200 Mbps (Raspberry Pi 3B+, 4, 5)

  - channel=36
  - ht_capab=[HT40+]
  - hw_mode=a
  - ieee80211ac=1

**<h3>Cellular Modem</h3>**

sudo nano /etc/udev/rules.d/hotpiauto.rules

- Quectel EC25

  - Vendor ID: **2c7c**
  - Product ID: **0125**

- SIMCom SIM7600

  - Vendor ID: **1e0e**
  - Product ID: **9001**

hotpipro@raspberrypi:~ $ lsusb  
Bus 001 Device 004: ID **1e0e**:**9001** Qualcomm / Option SimTech, Incorporated  
Bus 001 Device 003: ID 0424:ec00 Microchip Technology, Inc. (formerly SMSC) SMSC9512/9514 Fast Ethernet Adapter  
Bus 001 Device 002: ID 0424:9514 Microchip Technology, Inc. (formerly SMSC) SMC9514 Hub  
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub

**<h3>User Command</h3>**

- sudo hotpistart
- sudo hotpistop
- sudo hotpilist
- sudo hotpimount \<name\>
- sudo hotpiunmount \<name\>
- sudo hotpiread
- sudo hotpiwrite
- sudo hotpiupdate
