# Project name = DIY VR controller

## Controller Setup

1. Headset with Android phone + VRidge(RiftCat)
- Vridge software will view and emulate the head movement in 3-DOF(pitch,roll,yaw) from Android phone.

## Controller setup

1. Using GY-85 module also using combination sensor with MPU6050(Gyro+Accel) and Compass sensor(QMC555...)
-Sensor controller is using arduino Uno where it send serial communication to python

2. Button for controller is using a cheap ps controller(not original) and its emulated to xbox controller by x360ce.exe.
Freepie program will read the emulated xbox controller and emulated to hydra razer vr controller.

3. Working with camera to determine the x,y,z postion of controller and headset. The concept of using camera is to detect the
QR code from camera and emulated in python for its position and send it to Freepie software. The goal is to accomplish 6-DOF
with controller and the headset.

# Program flow

## There 4 input hardware that will be send to SteamVr.

1. Head 3-DOF(pitch,roll,yaw) motion from android phone working Vridge software.

- (Android Phone sensor --> Vridge App(android app) --> Wifi/Usb(Network communication)--> Vridge Software(PC)emulate -->SteamVr)

2. Controller 3-DOF motion from sensor working with Python code and Freepie software.

- (3-DOF motion sensor --> Arduino board --> Serial communication(USB) --> Python Code --> Freepie Software(PC)emulate -->SteamVr(Detect as Hydra Vr Controller))

3. QR code position from camera also working with Python code Freepie software.

- (Image camera --> Python code detect QR Code -- Calculate Position --> communicate with txt file --> Freepie read txt file and get data(emulate on Hydra controller position and freetrack data(For headset position)) --> Send to steamVr)

4. Button for PS controller.

- (Button Ps controller -->x360ce.exe --> Freepie --> SteamVr)
