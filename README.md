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

sudo hotpipro

**<h3>Wi-Fi Network</h3>**

sudo nano /etc/hostapd/hostapd.conf

**<h3>Cellular Modem</h3>**

sudo nano /etc/udev/rules.d/hotpiauto.rules

- Quectel EC25

  - Vendor ID: 2c7c
  - Product ID: 0125

- SIMCom SIM7600

  - Vendor ID: 1e0e
  - Product ID: 9001
