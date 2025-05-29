---
title: "Biped Gait - Walking Robot"
date: 2024-06-20
draft: false
description: "Very basic bipedal robot, to investigate parameter changes on gait and stability"
tags:
  - Control
  - Bipedal Gait
  - Forward / Inverse Kinematics
  - CAD modelling
  - Prototyping
image: "/images/BipedGait/BipedWalkingSide.gif"
featured: false
hide_feature_image: true
---

#### Demo of Best Walking Parameters

<iframe width="100%" height="450"
  src="https://www.youtube.com/embed/w4rrLuDohJY"
  title="Bipedal Robot Video"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>

Very simple robotic gait, still need to implement feedback control.

---

#### Showcase of Different Walking Parameters' Effect on Bipedal Gait

<iframe width="100%" height="450"
  src="https://www.youtube.com/embed/WKo5jZlnQE4"
  title="Bipedal Robot Video"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>

Shows the effects of stride delay, stride height, and stride length on the robotic gait. Also has an IMU attached to the head, so averaged acceleration data is plotted over a 10-second step period for comparison.

---

#### Need to Improve Grip and Weight Distribution

<div style="text-align: center;">
  <img src="/images/BipedGait/GripWalking.gif" alt="Grip Walking" class="slide-img">
</div>

<p>This better style of walking would allow the foot to raise and eliminate the 'sliding' behaviour observed.</p>

---

#### Sliding Behaviour

<p>See sliding and consequential angular rotation below on each step.</p>

<div style="text-align: center;">
  <img src="/images/BipedGait/StrideSliding.gif" alt="Stride Sliding" class="slide-img">
</div>