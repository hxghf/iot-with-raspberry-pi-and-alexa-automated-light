# iot-with-raspberry-pi-and-alexa-automated-light
automated light setup from vayun khare
Instructions:
Download "RASPBIAN STRETCH WITH DESKTOP" and unzip the zip file
https://www.raspberrypi.org/downloads/raspbian/

Download "win32diskimager--install.exe" program from following URL https://sourceforge.net/projects/win32diskimager/files/latest/download

Install "win32diskimager-1.0.0-install.exe"

Connect mini-sd card to a computer. In windows explorer right click your sd card drive letter and click on format menu. In format window select "FAT" in "File System" list and click start. Wait for the task to complete.



Launch "win32diskimager" program. Select image file "2017-04-10-raspbian-jessie.img" and your sd card drive letter and click "Write" (Wait for program to finish writing REAPBIAN image to the sd card)



Once image writing is completed, Copy "ssh" (ssh file is empty) and "wpa_supplicant.conf" files to root of the sd card. Open "wpa_supplicant.conf" in text editor and update ssid (wi-fi name) & password.

Insert the sd card into Raspberry Pi 3 and boot and wit for 10 seconds

In windows go to run & type "cmd" and type arp -a in command prompt. Look for "Physical Address" that starts with b8-27* & note the Internet Address. This is your Raspberry Pi3 Wi-fi IP address on your network.



Download "Putty.exe" from following URL https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

Run "Putty.exe" and type IP address in host name field and click start button & click yes to popup. On putty command line type in "pi" for "Login as:" & enter. For password enter "raspberry" and hit enter. You should see "pi@raspberrypi:~ $" prompt.



Type "sudo raspi-config" and go to "Interfacing Options" and enable VNC. Reboot pi3 by typing this command "sudo reboot". You will loose ssh connection.

 download and install VNC client on youe pc https://www.realvnc.com/download/vnc/windows/. Connect VNC to Respberry Pi3 using IP address. Login with user name "pi" and password "raspberry". You should see Pi3 desktop.



Launch Pi ssh session with putty or localy through VNC and type following two commands Pi command prompt to update it. "sudo apt-get update" and "sudo apt-get upgrade" (This will take a while)

Download this github project as zip file with following command "wget https://github.com/hxghf/iot-with-raspberry-pi-and-alexa-automated-light/edit/master/README.md/master.zip"

Unzip downloaded zip file with "unzip master.zip" command and type "cd IOT-Pi3-Alexa-Automation-master" command after unzip completes



Enter "sudo python3 RPi_name_port_gpio.py" command to run Pi IOT program

Give voice command to Alex to discover devices "Alexa discover devices" it will search your network and discover your Raspberry Pi 3 as an IOT device.

Give a voice command to Alexa "Turn on the office" you should hear a relay clicking sound and led turn on

Give a voice command to Alexa "Turn off the office" you should hear a relay clicking sound and led should turn off
