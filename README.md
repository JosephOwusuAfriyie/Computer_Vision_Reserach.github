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

# Proposed Methodology
The overall pipeline consists of the following stages:
DAWN Dataset ─────┐
                  ├──> Dataset Integration
ACDC Dataset ─────┘
                         │
                         ▼
                  Data Preprocessing
                         │
                         ▼
                   Real-ESRGAN
                  Image Enhancement
                         │
                         ▼
                  Train / Validation /
                      Test Split
                         │
                         ▼
                     YOLOv9
					 Object Detection Model
                         │
                         ▼
               Object Localization
                         │
                         ▼
             Performance Evaluation

# 1. Dataset Integration

Two open-source datasets were incorporated:
	•	DAWN — Detection in Adverse Weather Nature
	•	ACDC — Adverse Conditions Dataset with Correspondence
The datasets provide imagery representing challenging environmental conditions relevant to autonomous driving. The project focused particularly on:

	•	Fog
	•	Rain
	•	Snow
	•	Sandstorms
	
The DAWN dataset contains real-world traffic imagery across different road environments, while ACDC provides adverse-condition imagery captured under several challenging conditions. The merged dataset was processed to create a custom detection dataset representing diverse environmental conditions.

# 2. Data preprocessing

The dataset was:
	●	resized and augmented.
	●	annotated for object detection.
	
Organized into seven object classes:
	●	person
	●	bicycle
	●	car
	●	motorcycle
	●	bus
	●	truck
	●	traffic light

# 3. Image Enhancement
Real-ESRGAN was incorporated as an image super-resolution stage before object detection.
The motivation was to improve the visual quality of degraded images and provide the subsequent detection model with enhanced representations of objects that may otherwise be difficult to identify under poor visibility.

Adverse-weather image
          │
          ▼
     Real-ESRGAN
          │
          ▼
Enhanced image representation
          │
          ▼
       YOLOv9

# 4. Object Detection
YOLOv9 was used as the primary object-detection architecture. We trained the enhanced dataset using YOLOv9c with the GELAN-C pretrained architecture.
The experimental configuration included:
	●	Image size: 640 × 640
	●	Batch size: 8
	●	Epochs: 50
	●	GPU: Tesla T4
	●	Environment: Google Colab
	●	Framework/programming: Python
	
The model was trained to detect and localize relevant non-static objects within the adverse-weather imagery.
The study used a 70% training, 20% validation, and 10% testing split.

# 5. Model Evaluation
Model performance was evaluated using:
	•	Precision
	•	Recall
	•	F1-score
	•	Average Precision (AP)
	•	Mean Average Precision (mAP@50 and mAP@50-95)
	
These metrics evaluated the model’s ability to correctly identify and localize objects across different environmental conditions. A comparative analysis was also performed against a baseline YOLOv9 configuration without the Real-ESRGAN enhancement stage

# 6. Results
The experiments demonstrated strong detection performance across the evaluated weather conditions.
Weather Condition	Precision	Recall	mAP
Fog	                   98%	     89%    93%
Sandstorm	           92%	     89%	94%
Snow	               90% 	     85%	96%
Rain	               90%	     84%	96%

The results indicate that combining dataset integration, image enhancement, and YOLOv9 produced a strong detection pipeline across multiple adverse-weather scenarios.

For instance, the comparative analysis reported the following differences
between the proposed and baseline configurations:

	●	Rain: precision improved from 0.82 to 0.98; recall from 0.70 to
0.89; mAP@50 from 0.81 to 0.98.

	●	Snow: precision improved from 0.79 to 0.90; recall from 0.61 to
0.74; mAP@50 from 0.75 to 0.96.

These results support the project’s central hypothesis that preprocessing degraded imagery with a super-resolution model can contribute to improved downstream object-detection performance.


# Technologies & Tools
# Machine Learning / Computer Vision
	•	Python
	•	YOLOv9
	•	Real-ESRGAN
	•	Deep Learning
	•	Object Detection
	•	Image Super-Resolution
	•	Computer Vision
# Data
	•	DAWN
	•	ACDC
	•	Image preprocessing
	•	Dataset integration
	•	Data splitting
	•	Bounding-box annotations
# Evaluation
	•	Precision
	•	Recall
	•	F1-score
	•	Average Precision
	•	Mean Average Precision
# Supporting Tools
	•	Roboflow
	•	Git
	•	Google Colaboratory

# Key Research Contribution
This project contributed an experimental framework for adverse-weather
object detection by:

	●	integrating complementary adverse-weather datasets.
	●	incorporating super-resolution into an object-detection pipeline.
	●	applying YOLOv9c to multiple adverse-weather scenarios.
	●	evaluating performance across different environmental conditions.
	●	comparing the enhanced pipeline with a YOLOv9 baseline.
	●	identifying practical limitations associated with computational resources, image resolution, and dataset annotation.

This provides a foundation for future research into robust perception systems for autonomous vehicles.

# Potential future directions include:

	●	training with larger image resolutions
	●	evaluating larger and more diverse datasets
	●	investigating multimodal camera–LiDAR–radar fusion
	●	evaluating domain adaptation and cross-weather generalization
	●	testing newer object-detection architectures
	●	investigating uncertainty-aware detection for safety-critical autonomous systems
	●	evaluating latency and computational efficiency on edge hardware
	●	studying robustness under previously unseen weather conditions

# Research Relevance
This project forms the foundation of my broader research interest in robust computer vision, intelligent autonomous systems, and reliable
AI under uncertainty.

The work motivates several potential doctoral research directions, including:

	●	robust perception for autonomous systems
	●	multimodal sensor fusion
	●	uncertainty-aware object detection
	●	AI for safety-critical systems
	●	computer vision for healthcare and other high-consequence environments
	●	optimization of learning-enabled engineering systems.

# Reproducibility

The original experiments were developed in Python and executed using Google Colab. To reproduce the study, the implementation should include:

	1.	Acquisition and preparation of the DAWN and ACDC datasets.
	2.	Dataset harmonization and annotation.
	3.	Image preprocessing and Real-ESRGAN enhancement.
	4.	YOLOv9c/GELAN-C model initialization.
	5.	Training and validation under the documented configuration.
	6.	Evaluation against the baseline YOLOv9 configuration.
	7.	Analysis using precision, recall, F1, mAP@50, and mAP@50–95.

# Limitations and Future Work

The experiments were conducted using Google Colab and a Tesla T4 GPU, which constrained training duration and image resolution. The
experiments therefore used 50 epochs and 640 × 640 input images.
