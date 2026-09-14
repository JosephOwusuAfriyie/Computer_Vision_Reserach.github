# Object Detection and Localization
# Non-Static Object Detection and Localization in Adverse Weather Conditions for Autonomous Vehicles
A deep-learning-based computer vision project developed as part of my MSc in Computer Science at the University of Ghana. The project investigates how image enhancement and modern object-detection techniques can improve autonomous-vehicle perception under challenging weather conditions.

# Overview
Reliable visual perception is fundamental to autonomous driving. However, adverse weather conditions such as fog, rain, snow, and sandstorms can significantly degrade image quality and consequently reduce the ability of autonomous vehicles to detect and localize road users.
This project proposes a computer-vision pipeline that combines:
	•	Real-ESRGAN for image super-resolution
	•	YOLOv9 for object detection and localization
	•	A hybrid adverse-weather dataset constructed from DAWN and ACDC
	•	Quantitative evaluation using precision, recall, F1-score, AP, and mAP
The primary objective is to investigate whether enhancing image resolution before object detection can improve the perception of non-static objects, particularly pedestrians and vehicles, under adverse environmental conditions.

# Research Question
Adverse weather can introduce visibility degradation, noise, low contrast, occlusion, and other visual challenges that negatively affect autonomous-vehicle perception.
This raises an important research question:
How can computer-vision algorithms be combined to improve the detection and localization of non-static objects by autonomous vehicles operating under adverse weather conditions?
The project therefore investigates the integration of image super-resolution with object detection as a potential approach for improving perception reliability.

# Research Objectives
The project pursued three principal objectives:
	1.	Review existing state-of-the-art approaches for object detection and image-resolution enhancement.
	2.	Apply Real-ESRGAN to enhance the resolution of images captured under adverse weather conditions.
	3.	Develop and evaluate a YOLOv9-based object-detection model for detecting and localizing non-static objects.

🧠 # Proposed Methodology
