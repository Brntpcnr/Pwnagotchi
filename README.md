# Pwnagotchi

Pwnagotchi is an A2C-based “AI” powered by bettercap and running on a Raspberry Pi Zero W that learns from its surrounding WiFi environment in order to maximize the crackable WPA key material it captures (either by passive scanning or active deauthentication). This material is collected as PCAP files containing any form of handshake supported by hashcat, including PMKIDs, full and half WPA handshakes.

The purpose of this device is to give (ethical) hackers an excuse to learn about reinforcement learning and WiFi networking, also to give us a reason to get out for more walks.


The more you use this virtual pet, better and faster it gets at capturing handshakes and getting pcap files.

It has 3 modes:
MANUAL: When you connect your pwnagotchi through it's data port, you can get access to it using your pc via ssh port and the machine is kinda in like a sleeping mode. You can edit the configuration, add/remove/update
plugins, change it's color, change what will be displayed on it's screen etc. This is the mode you should be using your unit when you want to transfer data from/to it.

AUTO: When you connect your device through it's power port it starts scanning the nearby environment doing passive scans and active deauthentication attacks to capture handshakes. Whatever you adjust and configure in manual mode will be used in auto mode by default. This is the default mode your unit will start

AI: Pwnagotchi changes to this mode from AUTO mode by default. This is the mode where AI gets in the picture and uses its algorithm to how to be more successfull in its attacks. If it is a same modem that it captured the handshake of for example, it will use the fastest method to get it's handshake again. 

