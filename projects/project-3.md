---
layout: project
type: project
image: images/c_sharp.jpg
title: Sophomore Arduino Project
permalink: projects/sophomore-arduino-project
# All dates must be YYYY-MM-DD format!
date: 2016-12-16
labels:
  - Arduino
  - Adafruit 
  - C
summary: A “GPS Tracking Case Lock” with Arduino technology which has a fingerprint scanner lock and regularly sends GPS coordinates to an Android app.

---

<div class="ui small rounded images">
  <img class="ui image" src="../images/296 (1).jpg">
  <img class="ui image" src="../images/296 (2).jpg">
</div>

This project consists of two separate modules. The first module allows a user to enroll his or her fingerprint onto the Adafruit Fingerprint Scanner to activate the Lock-style Solenoid attached to the instrument case. This fingerprint communication to solenoid lock fully unlocks the case. The second module implements an Adafruit GPS Logger Shield that uses an HC-06 Bluetooth module, which sends longitude and latitude coordinates to a mobile Android app through Serial communication every five seconds. 

This project can be applied to any case that is wider, longer, and taller than five inches. Even if a person’s case gets stolen or misplaced, the GPS Tracking Case Lock allows the user to keep track of the case’s location and the ability to find their case. Though with this first working prototype, the person may not know the exact location of their case if stolen, their mobile phone app will tell them the last possible location of their case and will give the user a general idea of where their case may be found. Future modifications will consist of making the GPS’s sending range almost infinite as a user will not be limited to simply Bluetooth communication between the case and the app, but can be anywhere in the world and still be able to detect their case.

It is very important to take note that other competing products contain only one element or module of this project, from the HomCom Portable Safe Case with a Biometric Fingerprint Lock to the USCIS Case Status Android App. However, none of these competing products implement both elements of a fingerprint-based lock and a tracking device. Although there are more features that we would like to add to this project, such as a near virtually infinite GPS communication range to send coordinates from places or making the fingerprint sensor portable instead of it fixed to the exterior of the case, the GPS Tracking Case Lock can help people with valuable belongings feel more secure.

This first working prototype required two Arduino Unos and Adafruit products such as a Biometric Fingerprint Sensor, a GPS logger shield, a Motor shield, a 12 VDC Lock-style Solenoid, and an external 5V battery. However, for our solenoid to work properly, we needed another external battery that could supply 12 VDC and handle 1500mA of current which we then supplied.

I was the chief engineer of this project as I came up with this idea around early-July of 2016 and had started planning the necessary modules to implement it. It was not until I finalized a project partner did I share my idea and research-related materials. I set the proper dates and deadlines of every aspect of this project from getting each module to work separately to compiling all parts together toward a working prototype. 

I learned many important hardware concepts with this project as I was introduced to soldering, wiring, and overall design ideas. This project was very experimental as there was not a product that exhibited our exact design. From learning how a GPS module detects a fix to a satellite to wiring up a fingerprint sensor properly to attain the full 5V power necessary to even hours of debugging a C program, I felt as though this was a very productive project in learning simple methods that though alone may seem unimportant and trivial, together can form a huge potential marketable product.


Source: <a href="https://youtu.be/izAxeNXCFF8"><i class="large youtube icon "></i>YouTube/GPSTrackingCaseLock</a>
