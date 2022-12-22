# Launcher Password: uni1010

Make sure to leave a star if this repository helped you!

# Nerf Gun Call of Duty Warzone Controller (NGCODWC)

[Watch the video for this project here](https://youtu.be/ld0Pcy6F-3g)

![demo](https://github.com/AlfredoSequeida/readme_assets/blob/master/Nerf-Gun-Call-of-Duty-Warzone-Controller/gifs/demo.gif)

I had the idea of using a nerf gun as a controller to play Call of Duty Warzone, but since it's just a controller, it can work for any game with the rebinding of the keys. This repo contains all the files for the client and server, the android app used to get accelerometer data, and the 3D models for the buttons, buttons assembly, and other components.

## Setup
Python 3.5 or newer required.

### Client
The client is meant to be used on a Rasberry Pi. Before running it, you must install the dependencies. This can be done using the included setup.sh script:
```
sudo sh setup.sh
```
Then set up the script by setting the `SERVER_IP` in `nerf_client.py`

### Server
The server runs on the machine running the game to setup install the python dependencies use pip

```
py -m pip install -r requirements.py
```
Then set up the script by setting the `HOST` IP in `nerf_server.py`

## The build

### Nerf Gun
The nerf gun used for this build is the [NERF Fortnite AR-L Elite Dart Blaster](https://www.amazon.com/NERF-Fortnite-AR-L-Elite-Blaster/dp/B07MBK23M2). Even though I originally built this controller to play Call of Duty Warzone, this Fornite edition nerf gun provided the space I needed to add the buttons for in-game actions like moving around, plating, jumping, etc. It's also useful that it has more than one button already built into the gun, which I used for shooting (left mouse button), reloading (r), and ads (right mouse button).


### The Brains
For the brains of the build, I used the [Raspberry pi 4 Model B](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/). Since it has wifi built-in it lets us build a completely wireless solution. This is held on the gun using the bottom of this [Raspberry Pi 4 case project on thingiverse by John_Sinclair](https://www.thingiverse.com/thing:3723481)

![raspberry pi](https://imgur.com/GErPWCK.jpg)

### Power
To power the entire system we could just run a USB-c cable to the pi, however since I wanted to keep the build wireless, I used a portable solar chargeable USB power bank. This is the [Blavor Solar Charger Power Bank](https://www.amazon.com/dp/B07T2NRK8G/), which provides 5V at 2A. It's held in place with a custom 3D printed holder on the gun's shoulder rest.

![power bank](https://imgur.com/jjSDCQ5.jpg)


### Buttons
Buttons are designed to have a lead at the top and bottom components of a button. When I built it, I used aluminum foil to provide those contacts with a spring in between both components so the button rises back up.

The buttons should then be fed a voltage. In my case, I used the 3.3V source from the raspberry pi's GPIO pins. The other end of the lead is then connected to a GPIO pin that is used as an input. When these two leads make contact, the button will be registered as ON by the client python script.

![button assembly](https://raw.githubusercontent.com/AlfredoSequeida/Nerf-Gun-Call-of-Duty-Warzone-Controller/942de22107ea4fc2e7a0765d3b435ffa7a9f0cf2/mechanical%20drawings/button_assembly.svg)

The diagram above shows the setup for one button as an example, but the same setup applies to all of the buttons. With the correct standoff height, the button assembly can be held in with the pressure of the original screws that hold the gun together.

![buttons on gun](https://imgur.com/NiHnFBL.jpg)

### The Android App
The android app is used to get accelerometer information from an android phone, which is used to move the mouse pointer for in-game aiming. In my case, I used an old Nexus 5 that has a bad screen, so it was a great way to repurpose it. You can compile the app's source code using Android Studio.

![android app](https://i.imgur.com/SCM7iDE.jpg)

## Predicting Warzone Wins Based on Player Performance

### Author: <a href = 'https://github.com/aeddeb'> Ali Eddeb </a> 

![COD Banner](images/cod_banner.jpg)

In this project, I will be exploring what factors lead to more wins on COD Warzone - specifically the Battle Royale mode which is one of the most popular games being played in 2020.

I would like to create a model that can predict the probability a person can win games based on their skill, playstyle and stats. Then, I could make recommendations on how a user can improve their gameplay in order to increase the likelihood of winning Warzone matches.

I will be collecting player stats from various COD stat tracking websites through means of a scraper.

Currently, I am in the process of data collection.