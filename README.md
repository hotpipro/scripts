**<h3>Install HotPi Pro</h3>**

sudo wget -P /bin https://raw.githubusercontent.com/hotpipro/scripts/main/hotpipro

sudo chmod 755 /bin/hotpipro

sudo nano /bin/hotpipro

- wi-fi country code, network name, password

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

**Modem**&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**Vendor ID**&emsp;&emsp;&emsp;&emsp;**Product ID**

Quectel EC25&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;2c7c&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;0125

SIMCom SIM7600&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;1e0e&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;9001
