---
title: "Setting Up For Community VRAR Presentations"
date: 2024-08-04
---


## Desktop Installation
- Plug power cable
- Plug HDMI dummy


## Assisting Surface Installation
- Connect to router internet
- Use NoMachine to Remote


##  Pass connection through router

- Connect machine to Wifi
- Connect router to machine for power (type c)
- Connect router LAN to machine LAN using ethernet cable
- In Windows from network Connections Select  Wifi and ethernet and then right click -> Bridge connection
- You should have internet now




## Setting up for streaming Meta Quest video through USB locally (No Internet)

Setup Developer Mode on the Meta Quest


Cast View on A local window


Download scrcpy.exe at https://github.com/Genymobile/scrcpy


// Check that device is connected


adb devices 



// start tcp mode


adb tcpip 5555



// connect to ip (replace IP for correct IP)


adb connect 192.168.10.11:5555



// show screen


scrcpy



EXTRA

// find ip


adb shell ip route
