# Pwnagotchi

Pwnagotchi is an A2C-based “AI” powered by bettercap and running on a Raspberry Pi Zero W that learns from its surrounding WiFi environment in order to maximize the crackable WPA key material it captures (either by passive scanning or active deauthentication). This material is collected as PCAP files containing any form of handshake supported by hashcat, including PMKIDs, full and half WPA handshakes.

The purpose of this device is to give (ethical) hackers an excuse to learn about reinforcement learning and WiFi networking, also to give us a reason to get out for more walks.


The more you use this virtual pet, better and faster it gets at capturing handshakes and getting pcap files.

Disclaimer: This tool is created for educational purposes only, cracking and revealing network passwords can and probably will give birth to many unpleasant results for you dear reader. Be conscious and use your pet for good.

The purpose of this device is to give (ethical) hackers an excuse to learn about reinforcement learning, WiFi networking and reconnaissance and handshake processes, also to give us a reason to get out for more walks and socialize :)

The more we use our virtual pet, better and faster furthermore more efficient it gets at capturing handshakes and getting pcap files. Your device will keep on learning with you to optimize it’s efficiency.

Now I will tell you how I created my virtual pet step by step.

Hardware
Installation/Software
Configuration
Hardware:
Let’s begin with the hardware components I picked for my device:

A Raspberry Pi Zero W: The W version of Raspberry Pi Zero is required so that our device can scan Wi-Fi signals.

A micro sd card: A minimum of 8 gb sd card will be enough but to have better and faster utilization of my device I picked a 32gb sd card.

A micro-USB cord: Make sure to get a cable that supports data transfer, you will use the data port for data/file transfer and power port to power up your device. I use a shorter cable that just supports power mode when I’m out for a walk.

A portable power bank: The powerbank will be your battery once you go out walking your pet. But be careful that your powerbank doesn’t exceed the maximum voltage capacity of the Raspberry Pi Zero. I myself use a powerbank that has 6000 mAh capacity, 5V/2A input and 5V/2.1A output without any problems.

A screen display: You can connect your Pwnagotchi to you PC and look at it’s UI from the web browser but why not get a screen so you can look at your pet’s cute face while you are outside. For the screen I use a 2.13 inch Waveshare V4 which fits well with Raspberry Pi Zero W.

After gathering all the hardware parts I soldered the Raspberry Pi Zero W to the Waveshare V4 screen display using male pin headers. Following that you are free to put the parts all together in any way you desire to.

For my device to be portable I simply used tape to keep all the pieces together, it looks really handmade :) There are lots of other stuff you can use, you can 3d print yourself a case for your virtual pet. You can check for some alternatives from the link below:

https://www.pwnagotchi.com/products/pwnagotchi-case_1327965086_

For further assist in getting all the parts together and assembling them, you can check the links below:

https://www.youtube.com/watch?v=R-fTPv09vQ8

https://www.youtube.com/watch?v=gyKT_mASSuc&t=1288s



Installation and Software:

The Pwnagotchi is a project of many years and has undergone lots of changes/updates. So in order for you to not face any issues in the installation part I will tell you how I managed to install and use the latest version of the Pwnagotchi images, this part is important to get your device up and running properly. I will leave a video link also to watch the guide there and backtrack the process if there are some misconfigurations.

First go to this page and download the latest pwnagotchi image.

https://github.com/jayofelony/pwnagotchi/releases

After doing so, plug in your sd card. Now we will use balenaEtcher to flash the Pwnagotchi image into our sd card which will be the memory bank of our virtual device.

https://etcher.balena.io

Now open balenaEtcher and select the Pwnagotchi image file you wish to write to the sd card. Select the SD card you wish to write your image to. Be careful and wait before removing the SD card though, you will need to create one last file on it with the initial configuration so it runs properly.


Once we flash our image put the sd card into the Rasperry Pi and then connect the Raspberry Pi to your pc. Make sure to use the data port of the device and also a data cable to be able to change/edit/transfer files.

Now we will have to introduce our Raspberry Pi to our PC as a network adapter so that our device can connect to the internet, download/update plugins and ping other devices using our PC’s main network. To do so you need to download a file, you can find the link of it in the video I gave you the URL of at the end of this section.

And now we will edit the network adapter settings of our device so that it can use the internet and we can access our device using the ssh port through cmd.


The default settings to use are 10.0.0.1 for the IP and 255.255.255.0 for subnet mask
You may still face some issues regarding the network connection, in that case go to your main wi-fi adapter’s settings and share internet connection to the device.


Now we should be set. Connect to your device using ssh port. The default password is “raspberry” but you can change it once in the system.


To check for the network connection simply ping an IP adress.

Make sure that we have internet connection.

I would suggest you to use a file transfer program such as FileZilla in order to download files from your Pwnagotchi to your PC in a faster way.

https://filezilla-project.org

Here’s the link to the video that shows the correct installation of the latest software that I also used myself:

https://www.youtube.com/watch?v=OFxKN3N4gE8

Once the software installation is completed, we continue with my favourite part, the configuration.



Configuration:

Our dear Pwnagotchi has 3 modes:

MANUAL: When you connect your pwnagotchi through it's data port, you can get access to it using your pc via ssh port and the machine is kinda in like a sleeping mode. You can edit the configuration, add/remove/update
plugins, change it's color, change what will be displayed on it's screen etc. This is the mode you should be using your unit when you want to transfer data from/to it.

AUTO: When you connect your device through it's power port it starts scanning the nearby environment doing passive scans and active deauthentication attacks to capture handshakes. Whatever you adjust and configure in manual mode will be used in auto mode by default. This is the default mode your unit will start

AI: Pwnagotchi changes to this mode from AUTO mode by default. This is the mode where AI gets in the picture and uses its algorithm to how to be more successfull in its attacks. If it is a same modem that it captured the handshake of for example, it will use the fastest method to get it's handshake again. 


Once you plug in your device and get access through the ssh port, you access your system. The os that is used is Raspberry Pi OS which is similiar to Debian distribution of Linux. If you are a Linux user you will be really familiar with this system.


By default system settings there is a directory called “handshakes” where the .pcap files you captured will be downloaded into.

If you want to check/change the configuration settings for your device you can simply edit the /etc/pwnagotchi/config.toml file. You can add the wi-fi networks you don’t want your Pwnagotchi to “pwn”, edit the plugins that will be enabled/disabled, adjust the colour of your virtual pet, change your device’s name, save the .pcap files you captured to another directory etc.


To check for available plugins, you can run "pwnagotchi plugins list". You can use add/update/delete plugins the way you desire.

Visit the plugins page from the webpage of your device to see/enable/disable plugins. Simply visit “10.0.0.2:8080/your_devices_name/plugins”

This way you can simply enable/disable your plugins the way you like.


I suggest you to search more about the plugins and check the original Pwnagotchi repository to find more information about them. That way you can customize your Pwnagotchi the way you want. Enable and disable plugins to see which ones are more efficient and suit you the most. More you understand how the device and it’s plugins work, you will use it more efficiently and have more fun while doing so.

Now we have a fully operating virtual pet that captures handshake files from it’s surrounding wi-fi environment. To learn more about Pwnagotchi check the official website.

https://pwnagotchi.ai/intro/

