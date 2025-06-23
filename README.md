HOTPI PRO INSTALLATION INSTRUCTIONS

1. Connect your Raspberry Pi to the internet.

2. Download the script by entering the following command in the terminal:

  sudo wget -P /bin https://raw.githubusercontent.com/hotpipro/scripts/main/hotpipro

3. Edit your Wi-Fi country code, network name, and password by entering the following command in the terminal:

  sudo nano /bin/hotpipro

4. Save your changes and exit the editor by pressing CTRL+X, then Y, then ENTER on your keyboard.

5. Make the script executable by entering the following command in the terminal:

  sudo chmod 755 /bin/hotpipro

6. Install the script by entering the following command in the terminal:

  sudo hotpipro

Your Raspberry Pi will reboot and you are done.
