---
layout: post
title: "Software Application for 3D Endoscope"
author: "Napassorn"
categories: resources
tags: [resources]
image:
  feature: flexible-endoscope.jpg
---

# [Software Application for 3D Endoscope](https://github.com/Larnx)  

## Introduction 
For my senior design project at Boston University, I am working with 2 engineering students to develop a software application, LARNX, that reads 2D and 3D endoscopic images and videos, and ultimately produces quantitative information such as:   

**Volume and Surface area of residue objects** in the throat (For 3D videos only)

**Percentage of the hypopharynx covered with residue** (for both 2D and 3D videos)  

If successful, this application coupled with the current 2D and 3D endoscopy technology will eliminate the subjective ambiguity that clinicians face when assessing and diagnosing [dysphagia]({{ site.github.url }}{% post_url 2017-11-12-Dysphagia %}). This will allow for faster, more-accurate diagnosis, and more-effective treatment, and ultimately it will save lives and prevent unnecessary deaths!   

![Logo]({{ site.github.url }}/assets/img/logoTC.png)

## Deliverables
We aim that our software tool can:

**Measure the volume of residue remaining in the hypopharynx** as visualized by the 3D endoscope. More broadly, the software required to do this should be able to measure residue abnormalities as visualized by a 3D video or image within an enclosed volume (such as the hypopharynx, or a replica model of the throat). 

**Calculate the percentage of area covered with residue** in the hypopharynx as visualized by the 3D endoscope.  Again, more broadly this can apply outside of the hypopharynx and in the case of a replica model of the throat. 

Conduct these measurements either **in real-time or in post-processing** if real-time is not feasible.

**Display the results of the analysis in a clean, user friendly interface** that nicely wraps the underlying algorithms. This should ultimately be an application that clinicians use. 

**Provide comprehensive documentation** for using the the software.  

## Design Model
We divided our work on the software into the [front end](https://github.com/Larnx/Larnx_User_Interface) and the [back end](https://github.com/Larnx/Larnx_Back_End).

### Front End
The front end is the user interface/ desktop application written in HTML, CSS, JavaScript (Node.js) using the [Electron](https://electron.atom.io/) platform.

### Back End
The back end holds the video-processing algorithms written in C++ and utilizes the [OpenCV Library](https://opencv.org/) to conduct the following:  

#### Implementation  

The LARNX back-end executable is designed to be modular and easily compatible with the front-end. The general structure is a main() file that takes in commands from the user interface, and then parses these commands to call the appropriate handler function which then executes the appropriate video-processing algorithm in the back-end. In other words, a user presses a button, that button intiates a command that runs the script in the back-end. The back-end conducts the script and delivers the results back to the user interface.  

Some current methods operating in the back end include:

##### Image/Video Acquisition (2D and 3D)    
  
The new 3D endoscope comes with a built in software and API written in C++. We were think of streaming the video captured from the  
endoscope through this API. This makes it possible to do quantifications in real-time.  

There is also an option for doctors to upload a recorded video or images for post-processing as well. Doctors then have the option of 
doing still frame analysis, selecting frames for comparing the residue amounts in each frame (our software will be able to calculate 
the volume, surface, area, and percentage of throat covered in each 3D frame).   
   
##### Object segmentation (2D and 3D)   
  
The diagnostic approach to dysphagia is the endoscopic swallow study. The patient swallows different consistencies of food (thin, puree, and hard). Puree and hard food are dyed in green and thin is dyed in white. Given the red hue nature of the hypopharynx, the color of dyed food residue in throat is drastically distinct, making it possible to be detected via OpenCV color based segmentation algorithms. Currently, I am developing an algorithm that detect the residue in the throat from recorded 2D endoscope videos using the HSV (Hue, Saturation, Value) color model because I found that it is more accurate for object detection than the default RGB color model. In choosing to detect green hue, the algorithm produces data ratio of the green pixel values for each frame in the video. This can easily be plotted to qualitatively show the amount of residue in throat per video frame.   

However, using a color based segmentation algorithms allows to detect one color at a time. I will need to improve this algorithm to generalize to other hues. Stay tuned!  
   
##### Object Tracking (2D and 3D)  

I am currently looking into the different modes of object tracking. Though Blob detection is one option, it is an independent algorithm. Ideally, I want to fuse this algorithm with the object segmentation algorithm above. In tracking the residue object, I intend to simply draw squares around clusters of residues in each video frame.   
   
##### Surface Area and Volume Quantification (3D)   
  
3D video and images provide additional data that can be used to calculate the volume. This data is distance. The 3D stereoscopic 
cameras provide the distance from the camera to the back of the throat, and the distance from the camera to the top of the 
residue. With the right scaling, the surface area can be calculated. To calculate volume, we have to assign some coordinate system and do some math to get the volume out.     
   
Our final deliverable is due in March 2018, so stay tune for any updates!  

   
[Photo Credits](https://www.voicedoctor.net/diagnosis/voice/anatomy)
   
