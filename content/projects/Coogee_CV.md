---
title: "Automated Production Monitoring"
date: 2025-04-01
draft: false
description: "Real-time object detection with live camera feed to optimize operational performance"
tags:
  - Computer Vision
  - OpenCV
  - YoloV8
  - TensorFlow 
  - PLC 
  - RTSP 
  - Real Time Inference 
  - Digital-Analog I/O
image: "/images/Coogee/CVDU_cover.gif"
featured: true
---

### Overview
- Real-time object detection and instance segmentation via live camera of industrial machinery to optimize operational performance. Full ML pipeline, labelling, training, inference and deployment.

Application of Python, OpenCV, PyTorch, TensorFlow, YOLOv8, Detectron2, PLCs for automation.

### Video Demo

<iframe width="880" height="520" src="https://www.youtube.com/embed/63AH2FNjILU" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- Show custom_trained model detecting the different belt classes during operation.
- Setup for both real-time RTSP stream of plant CCTV footage and recorded mp4 footage for testing
- Graph displays real-time class outputs for easier visual reference
- Data is logged in Real Time 
- Digital outputs Sending HIGH and LOW signals via NIDaq (National Instruments Digital to Analag Converter)
- Communicates directly with Siemens PLC



### Additional ML Projects Implemented on CCTV footage: 
- Inference analysing the status of machine, capable of sending alerts when machine breaks 
- Improvements needed to predict / stop the machine before it breaks 

![Atomiser Start](/images/Coogee/Atomiser_inferece.gif)
<br>
</br>
![Atomiser Break](/images/Coogee/Atomiser_break.gif)