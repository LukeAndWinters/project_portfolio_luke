---
title: "Biped Gait - Walking Robot "
date: 2024-06-20
draft: false
description: "Very basic bipedal robot, to investigate paramter changes on gait and stability"
tags:
  - Control 
  - Bipedal Gait 
  - Forward / Inverse Kinematics 
  - CAD modelling
  - Prototyping 
image: "/images/BipedGait/GripWalking.gif"

featured: false
hide_feature_image: true
---
#### Demo of Best Walking Parameters  
<iframe width="100%" height="450" 
  src="https://youtu.be/w4rrLuDohJY" 
  title="Bipedal Robot Video" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

Very simple robotic gait, still need to implement feedback control. 

#### Showcase of different walking Parameters effect on Bipedal Gait  
<iframe width="100%" height="450" 
  src="https://youtu.be/WKo5jZlnQE4" 
  title="Bipedal Robot Video" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>

Shows the effects of Stride Delay, Stride Height and Stride Length on the robotic gait. Also has IMU attached to head,so average out acceleration datea is plotted for a 10 second step period for comparison. 

<br>
</br>

#### Need to improve grip and weight distribution

<img src="/images/BipedGait/GripWalking.gif" alt="ChessBot Side View" class="slide-img">

This better style of walking would allow the foot to raise and eliminate the 'sliding' behvaiour observed

<br>
</br>

#### Sliding Behvaiour 
See sliding and consequential angular rotation below on each step 

<img src="/images/BipedGait/StrideSliding.gif" alt="ChessBot Front View Animation" class="slide-img">

