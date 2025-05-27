---
title: "Drone Patrol Beach Safety System "
date: 2024-11-12
draft: false
description: "An autonomous drone patrol swarm for hazard detection and beach safety monitoring"
tags:
  - Multi-Agent Control Theory
  - YOLOv8
  - Unity HDRP 
  - Computer Vision 
  - Customer Interaction
image: "/images/Capstone/IMG_cropped_setup.png"
featured: false
hide_feature_image: true
---

Multiple drones autonomously patrol a beach, they use a Machine Learning model to detect common beach hazards such as **sharks**, **rip-currents** and **swimmers**. Hazard locations and human Surf-Life-Saver (SLS) input is used in Multi-Agent Control Theory to optimally path the drones based on SLS input - assisting with emergency response and coverage.

Proof-of-concept drone patrol network made in collaboration with the SharkSmart Drone Trial Surf-Life Savers members.


## Project Demo

<iframe width="100%" height="670" 
  src="https://www.youtube.com/embed/-2F_cr2FCYE"
  title="Drill Video - Mechatronics Systems Design" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

<div style="display: flex; gap: 2rem; flex-wrap: wrap; justify-content: space-between;">
  <br>
  <div style="flex: 1; min-width: 250px;">
    <h5>Asset Labels: </h5>
    <ul>
      <li><strong>Pink Squares</strong> – Drone Camera Field of View (FoV)</li>
      <li><strong>Green Circle</strong> – Human Swimmer outline</li>
      <li><strong>Red Circles</strong> – Shark outline</li>
    </ul>
  </div>

  <div style="flex: 1; min-width: 250px;">
    <h5>Mapping Labels: </h5>
    <ul>
      <li><strong>Orange</strong> – Uncertainty Regions</li>
      <li><strong>Red Gaussians</strong> – Interest Regions (Manually dropped with human input)</li>
    </ul>
  </div>

</div>

<h5>Side Bar :</h5>  

**Spawners**: Can spawn in humans, sharks, rocks and patrolling drones.  
**Importance**: Adjust the uncertainty and interest metrics to influence drone pathing


#### What Surf Life Savers See

<iframe width="100%" height="450" 
  src="https://www.youtube.com/embed/CNZuJp-y8Og" 
  title="YouTube video" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

In this video when a shark is detected, it shows the camera in red, and automatically switches to that drones video feed. 

All the drone views are streamed to monitor(s) in the SLS tower, when detections are made it sends an alert, so they can review the appropriate camera, and make decisions based on this information. E.g. A shark is spotted by a patrolling drone, the life-saver can verify this and receive continuosu location updates from the drone. 

<br>
</br>
 

## High-Level System Overview

**Aims and Objectives:**
1. Develop an autonomous system to patrol Dynamic Envionments for items of interest using CV and multiple UAVs
2. Construct a Proof of Concept using high-fidelity beach simulation for data collection and testing
3. Tailor the output and desired swarm behaviour to the needs of the Australian Surf-Lifesavers 

<img class="slide-img" src="/images/Capstone/Slides/Slide10.png" alt="Slide 10">

Project Used 3 Components:
1. **Simulation:** Proof of Concept Beach Environment
2. **Machine Learningn:** Data Collection and Hazard Detection 
3. **Multi-Agent Control** Theory: Optimal Drone Pathing 
The System allows multiple drones to autonomously patrol a beach, we desigend the ML pipeline to collect training data using a drone sweep to train a custom shark, human and rip detection model. 

The video above shows how the drones patrol behaviour can altered: Either following hazards or exploring based on how the 'importance' sliders are adjusted. 

The model supports up to 5 autonomous drones at the same time, and the behvaiour can be explored by experimenting with the sliders. 

This was implemented so that SLS could tune the design, preferencing hazards they deem more important (e.g. following a shark) or instructing the drone to explore new areas, by manually dropping interest points. 

System intended as an extension to the already in-operation SharkSmart Drone trail in NSW and Queensland to help reduce emergency response time, provide critical information to live-savers and increase their coverage capabilities. 

<br>
</br>

## Multi-Agent Control Highlights

Unique application of tunable *Interest* and *Uncertainty* to influence drone pathing. 


<iframe width="100%" height="450" 
  src="https://www.youtube.com/embed/ybDFZZm3nlQ" 
  title="YouTube video" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

<br>
</br>

#### Uncertainty
- **Blue - Green:** shows linearly increasing uncertainty function. Drones are driven to explore uncertain areas. The drone FOV (underneath the drone) is 0 Uncertainty. Inversse importance function (further away). Encourages drones to explore the area around itself, that is the least recently seen. 

<img class="slide-img" src="/images/Capstone/Slides/Slide37.png" alt="Slide 37">

<br>
</br>

#### Interest 
- **Red - White:** Particular points drones are driven to explore. (These are created from hazard detections e.g. spotting a shark)

<img class="slide-img" src="/images/Capstone/Slides/Slide36.png" alt="Slide 36">

##### *Weighed(Uncertainy) + Weighted(Interest) = Drone Path*
<img class="slide-img" src="/images/Capstone/Slides/Slide38.png" alt="Slide 38">

<br>
</br>

#### Search Area and Partitions
<img class="slide-img" src="/images/Capstone/Slides/Slide35.png" alt="Slide 35">

<br>
</br>

## Machine Learning Highlights 
#### Data Collection - Simulation View 
<iframe width="100%" height="450" 
  src="https://www.youtube.com/embed/mQIK8UEKytU" 
  title="YouTube video" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

Shows the drone sweep path with full density scene with as many assets as possible: Sharks, humans, rocks, rips currents. 

#### Data Collection - Drone View 
<iframe width="100%" height="450" 
  src="https://www.youtube.com/embed/3GwQIhXPZyw" 
  title="YouTube video" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

Drone view during the data collection, can see the automated object detection labels and bounding boxes. Created Pipeline, code that automatically formats the output for YoloV8 Training. 

#### Training results 
<img class="slide-img" src="/images/Capstone/Slides/Slide30.png" alt="Slide 30">

<br>
<br>

## Simulation Highlights

<img class="slide-img" src="/images/Capstone/Slides/Slide14.png" alt="Slide 14">
<br>
</br>
<img class="slide-img" src="/images/Capstone/Slides/Slide16.png" alt="Slide 16">
<br>
</br>

<iframe width="100%" height="450" 
  src="https://www.youtube.com/embed/61w9dEtJFhY" 
  title="YouTube video" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

<br>
<br>

#### Won the "People's Choice Award" 
We were awarded the People's Choice Award receiving the most votes out of over 300 Capstone Projects during the Endeavour Exhibition, where we presented to businesses, academics and relatives of Capstone students.

<img src="/images/Capstone/IMG_award.JPG" alt="Endeavour Award Ceremony" style="width: 100%; max-width: 800px; display: block; margin: 0 auto;">


<br>
<br>

## Full Presentation Slides 
Our Full Final Presentation Slides can be seen below. If you would like even more detail on the project, contact us as we will send you our full project report. 

[View Full Presentation Slides]({{< ref "capstone_slides.md" >}})

<a href="/projects/capstone_slides/">
  <img class="slide-img" src="/images/Capstone/Slides/Slide1.png" alt="Slide 1">
</a>