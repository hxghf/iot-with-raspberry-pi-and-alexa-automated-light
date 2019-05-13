automated light with pi and alexa
so first on your pi connect a relay to pin 7 and another on 11 and connect the others to gnd and 5V respectively and connect your light to the relay and you need to setup the pi and alexa on your own links to buy
*THESE ARE THE OFFICIAL LINKS YOU CAN BUY THE SAME FROM AMAZON ETC. FOR CHEAPER PRIZES*(the relay is from amazon)THESE MIGHT NOT BE IN STOCK
relay:https://www.amazon.in/REES52-5VRELAY-Channel-Arduino-Raspberry/dp/B01HXJDBII?tag=googinhydr18418-21&tag=googinkenshoo-21&ascsubtag=_k_CjwKCAjwq-TmBRBdEiwAaO1en1v2e-Va-OnJJ5MdwpQjFp5ImoLM2h7qO6wKa3O6uUPubl3lrHaP8BoCCasQAvD_BwE_k_&gclid=CjwKCAjwq-TmBRBdEiwAaO1en1v2e-Va-OnJJ5MdwpQjFp5ImoLM2h7qO6wKa3O6uUPubl3lrHaP8BoCCasQAvD_BwE
raspberry pi 3 B+:https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/
Alexa Echo Dot:https://www.amazon.in/Echo-Dot-2nd-Gen-speaker/dp/B071NB4PGV
you can use any type of alexa but only alexa not google home or anything and you can use a different pi but it might not be same or not even work and the "Good Night" command i added myself on the alexa app it is not in the code
## Instructions:

1. Download "RASPBIAN STRETCH WITH DESKTOP" and unzip "raspbian-jessie.zip"
  https://www.raspberrypi.org/downloads/raspbian/

1. Download "win32diskimager-1.0.0-install.exe" program from following URL
  https://sourceforge.net/projects/win32diskimager/files/latest/download

1. Install "win32diskimager-1.0.0-install.exe"

1. Connect mini-sd card to a computer. In windows explorer right click your sd card drive letter and click on format menu.
  In format window select "FAT" in "File System" list and click start. Wait for the task to complete.
  
    ![alt text](https://raw.githubusercontent.com/nassiramalik/IOT-Pi3-Alexa-Automation/master/images/formatsdcard.jpg)
  
1. Launch "win32diskimager" program. Select image file "2017-04-10-raspbian-jessie.img" and your sd card drive letter and click "Write"
  (Wait for program to finish writing REAPBIAN image to the sd card)
      
    ![alt text](https://raw.githubusercontent.com/nassiramalik/IOT-Pi3-Alexa-Automation/master/images/win32diskimager.jpg)

1. Once image writing is completed, Copy "ssh" (ssh file is empty) and "wpa_supplicant.conf" files to root of the sd card. Open "wpa_supplicant.conf" in text editor and update ssid (wi-fi name) & password.

1. Insert the sd card into Raspberry Pi 3 and boot and wit for 10 seconds

now connect your pi to a power source and hdmi then set up your pi after it is completed (you know it when your background changes to a desktop like a real computer) then on the top bar there are apps open the terminal the one with a black box and in it ">_"
click it then type "ifconfig" then under the line "wlan0:" find "inet" next to it there will be your pi's ip address copy it then

1. Download "Putty.exe" from following URL https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

1. Run "Putty.exe" and type IP address in host name field and click start button & click yes to popup. On putty command line type in "pi" for "Login as:" & enter. For password enter "raspberry" and   hit enter. You should see "pi@raspberrypi:~ $" prompt.

    ![alt text](https://raw.githubusercontent.com/nassiramalik/IOT-Pi3-Alexa-Automation/master/images/puttypi3prompt.png)

1. OPTINAL-Type "sudo raspi-config" and go to "Interfacing Options" and enable VNC


    ![alt text](https://raw.githubusercontent.com/nassiramalik/IOT-Pi3-Alexa-Automation/master/images/pi3vnc.png)
1. Launch Pi ssh session with putty or localy through VNC and type following two commands Pi command prompt to update it. "sudo apt-get update" and "sudo apt-get upgrade" (This will take a while)
1. Download this github project as zip file with following command
  "wget https://github.com/hxghf/iot-with-raspberry-pi-and-alexa-automated-light/edit/master/README.md/master.zip"
1. Unzip downloaded zip file with "unzip master.zip" command and type "cd IOT-Pi3-Alexa-Automation-master" command after unzip completes

1. Enter "sudo python3 RPi_name_port_gpio.py" command to run Pi IOT program
1. Give voice command to Alex to discover devices "Alexa discover devices" it will search your network and discover your Raspberry Pi 3 as an IOT device.
1. Give a voice command to Alexa "Turn on the office" you should hear a relay clicking sound and led turn on
1. Give a voice command to Alexa "Turn off the office" you should hear a relay clicking sound and led should turn off
