HOTPI PRO INSTALLATION INSTRUCTIONS

Connect your Raspberry Pi to the internet.

Download the script by entering the following command in the terminal:
sudo wget -P /bin https://raw.githubusercontent.com/hotpipro/scripts/main/hotpipro

Edit your Wi-Fi country code, network name, and password by entering the following command in the terminal:
sudo nano /bin/hotpipro

Save your changes and exit the editor by pressing CTRL+X then Y then ENTER on your keyboard.

Make the script executable by entering the following command in the terminal:
sudo chmod 755 /bin/hotpipro

Install the script by entering the following command in the terminal:
sudo hotpipro

Your Raspberry Pi will reboot and you are done.
