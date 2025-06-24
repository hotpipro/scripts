HOTPI PRO INSTALLATION INSTRUCTIONS

Connect your Raspberry Pi to the internet.

Download the script by entering the following command in the terminal:

sudo wget -P /bin https://raw.githubusercontent.com/hotpipro/scripts/main/hotpipro

Edit your Wi-Fi country code, network name, and password by entering the following command in the terminal:

sudo nano /bin/hotpipro

Save your changes and exit the editor by pressing CTRL+X, then Y, then ENTER on your keyboard.

Make the script executable by entering the following command in the terminal:

sudo chmod 755 /bin/hotpipro

Install the script by entering the following command in the terminal:

sudo hotpipro

Your Raspberry Pi will reboot and you are done.

NOTE: The script will run as is without any modifications; however, it is recommended to edit the "country_code=", "ssid=", and "wpa_passphrase=" parameters, as the country code is set to "US", the network name is set to RPI-5G, and the password is set to "password" by default. Please locate "# EDIT THE FOLLOWING SECTION:" within the script. Your Wi-Fi country code must be capitalized, your network name must have 1-32 characters, and your password must have 8-63 characters. Do not remove the apostrophe at the end of your password, as it is required for the script to install properly. Failure to follow these instructions correctly will result in your Wi-Fi access point not working or the script not installing properly.
