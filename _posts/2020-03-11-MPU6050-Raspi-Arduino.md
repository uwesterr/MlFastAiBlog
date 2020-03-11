---
toc: true
title: Develop Android app to park a camper level
description: How to develop an Android app using a MPU6050 and a Raspi to help parking a camper level
categories: [Raspi,  MPU6050, Android]
image: images/vsCodeSreenShot.png
comments: true
---
# Develop Android app to park a camper level


--- 

In the blog [Rotationssensor MPU-6050 mit WebGL am Raspberry Pi visualisieren](https://tutorials-raspberrypi.de/raspberry-pi-mpu-6050-rotationssensor-webgl-nodejs-server/)
>Der Raspberry Pi ist zu vielem in der Lage, so können einfach Rotations- und Beschleunigugnswerte mittels eines Sensors, wie dem MPU-6050, ausgelesen werden. Das Ergebnis sind jedoch einfache Zahlen, worunter man sich im Normalfall nicht all zu viel vorstellen wird. Jedoch ist es sehr einfach diese Zahlen zu visualisieren. Dies geht in modernen Browsern ganz einfach mittels WebGL, womit man 2D und 3D Objekte im Browser rendern kann.

 <figure>
  <img src="images/MpuWiringRapsi.png" width="20%" height="20%" class="center">
  <figcaption>Sensor MPU 6050</figcaption>
</figure> 


## VNC: Remote access a Raspberry Pi

Setting up a VNC connection from phone to the raspi follow the instructions given at

https://magpi.raspberrypi.org/articles/vnc-raspberry-pi



## Setting up a Raspberry Pi as a Wireless Access Point

Setting up the raspi as a wireless access point so that you can use VNC on a camping ground follow instructions given at https://www.raspberrypi.org/documentation/configuration/wireless/access-point.md 
This documentation assumes that we are using the standard 192.168.x.x IP addresses for our wireless network, so we will assign the server the IP address 192.168.4.1. 

**Note:** Change default in `sudo nano /etc/hostapd/hostapd.conf` to something meaningful to you

```
ssid=NameOfNetwork # change this
hw_mode=g
channel=7
wmm_enabled=0
macaddr_acl=0
auth_algs=1
ignore_broadcast_ssid=0
wpa=2
wpa_passphrase=AardvarkBadgerHedgehog # change this
```

## Measuring Rotation and acceleration with the Raspberry Pi

Follow instructions at https://tutorials-raspberrypi.com/measuring-rotation-and-acceleration-raspberry-pi/
