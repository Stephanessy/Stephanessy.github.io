---
title: "Embedded Challenge Term Project Embedded Sentry"
collection: projects
permalink: /projects/embedded-challenge-term-project-embedded-sentry
excerpt: 'Used microcontroller and Inertial Measurement Unit to design a system in C++ that can record and recognize hands movements, which could be further used in smart locks system as extra verification method.'
start: 2020-4-1
end: 2020-6-1
---
## Requirements
board: SAMD21 Xplained Pro  
IMU: MPU6050  
IDE: Arduino  
## Introduction
This project is used to record and detect gestures using Kalman filter and DTW algorithm.  

Use the data collected from a single accelerometer (MPU6050) to record a hand movement sequence as a means to generally “unlock” a resource. The sequence is recorded multiple times. Recorded sequence is saved on the microcontroller (SAMD21 Xplained Pro). A successful unlock is indicated by LED.  

Used Kalman filter to smooth the time sequence and Dynamic Time Warping (DTW) algorithm to match patterns, achieving about 70% accuracy on complicate movements detection.

[Link for the project](https://github.com/Stephanessy/EmbeddedChallenge2020)
