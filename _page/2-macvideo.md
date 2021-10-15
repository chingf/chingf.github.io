---
layout: article
title: Brain-Machine Interface Video Processing Application
permalink: /projects/macvideo.html
cover: /ching-photos/feedback.jpg
---

Added features to an existing macOS app for mouse brain-machine interface: implementation of a closed-loop system for data processing and feedback control with Arduino (details at below link). Developed in Swift with Xcode. 

Specifically, users can now upload ROI coordinates and radii. The app will get the running z-score of the fluorescence, and deliver feedback to the mouse given some user-definted fluorescence threshold and reset values. Feedback is delivered in the form of audio feedback and an Arduino TTL pulse. The Arduino pulse can be connected to electrical stimulation of the reward center of the brain: the ventral tegmental area. 

<!--more-->

Github repo available [here](https://github.com/chingf/CarmenaCamera). This application was developed as part of a brain-machine interface (BMI) project in the Carmena lab of UC Berkeley. The goal was to implement a chronic BMI in the homecages of mice.