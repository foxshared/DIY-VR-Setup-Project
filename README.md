# Project name = DIY VR controller

## Headset Setup

1. Headset with Android phone + VRidge(RiftCat)
- Vridge software will view and emulate the head movement in 3-DOF(pitch,roll,yaw) from Android phone.

2. Using Camera to get the position head with QR code. To accomplish 6-DOF with head tracking.

## Controller setup

1. Using GY-85 module or using combination sensor with MPU6050(Gyro+Accel) and Compass sensor(QMC555...)
the data will be read in arduino Uno board and send it via serial communication to PC with python program.

2. Button for controller is using a playstation controller(not original) and its emulate to xbox controller by x360ce.exe.
Freepie program will read the emulated data of x360ce program and emulated its again to hydra razer Vr Controller data for use in SteamVr.

3. Working with camera to determine the x,y,z postion of controller. The concept of using camera is to detect the
QR code from camera and emulated in python for its position and send it to Freepie software. The goal is to accomplish 6-DOF
with controller.

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
