#Cameras #Vision #Applications

## What can be done with cameras?
Cameras are one of the richest sensors in robotics and are used for:
* **Navigation**: Lane detection, visual odometry (tracking movement).
* **Control**: Visual-servo control (using image features to guide a robot).
* **Perception**: Object detection and recognition, face recognition.

## Summary
* **Resolution, frame rate, and color model** all affect how you must read and process image data.
* **Frame rate $\neq$ processing rate**. The time it takes your computer to *process* an image is often much longer than the time it takes to *acquire* it. This lag will impact your navigation and control loops.
* **Computer vision** is a well-established field with many available resources and algorithms.