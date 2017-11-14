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
For my senior design project at Boston University, I am working with 2 engineering students to develop a software application LARNX that can read 2D and 3D endoscope images and videos, and quantitatively compute the surface area and volume of residue (from 3D videos only) in the throat and the percentage of the hypopharynx that is covered with residues (from both 2D and 3D videos). If successful, this application coupled with the current 2D and 3D endoscopy technology (insert 3D specs here) will eliminate the subjective ambiguity that clinicians face when assessing and diagnosing [dysphagia]({{ site.github.url }}{% post_url 2017-11-12-Dysphagia %}). This will allow for faster, more-accurate diagnosis, and more-effective treatment, and ultimately it will save lives!   

![Logo]({{ site.github.url }}/_assets/img/logoTC.png)

## Deliverables
We aim that our software tool can:

**Measure the volume of residue remaining in the hypopharynx** as visualized by the 3D endoscope. More broadly, the software required to do this should be able to measure residue abnormalities as visualized by a 3D video or image within an enclosed volume (such as the hypopharynx, or a replica model of the throat). 

**Measure the percentage of area covered with residue** in the hypopharynx as visualized by the 3D endoscope.  Again, more broadly this can apply outside of the hypopharynx and in the case of a replica model of the throat. 

Conduct these measurements either **in real-time or in post-processing** if real-time is not feasible.

**Display the results of the analysis in a clean, user friendly interface** that nicely wraps the underlying algorithms. This should ultimately be an application that clinicians use. 

## Design Model
We divided our work on the software into the [**front end**](https://github.com/Larnx/Larnx_User_Interface) and the [**back end**](https://github.com/Larnx/Larnx_Back_End).

### Front End
The front end is the user interface/ desktop application written in HTML, CSS, JavaScript (Node.js) using the [Electron](https://electron.atom.io/) platform.

### Back End
The back end holds the video-processing algorithms written in C++ and utilizes the [OpenCV Library](https://opencv.org/) to conduct the following:  

#### Implementation  

The final LARNX back-end executable is designed to be modular and easily up-dated in the front-end. Hence, the general structure is a main() file that takes in commands from the user interface, and then parses these commands to call the appropriate handler function which then executes the appropriate video-processing algorithm in the back-end.

Some current methods operating in the back end include:

**Image/Video Acquisition (2D and 3D)**:    
  
The new 3D endoscope comes with a built in software and API written in C++. We were think of streaming the video captured from the  
endoscope through this API. This makes it possible to do quantifications in real-time.  

There is also an option of doctors uploading a recorded video or images for post-processing as well. Doctor then have the option of 
doing still frame analysis, saving frames for comparing the residue amounts in each frame (our software will be able to calculate 
the volume, surface, area, and percentage of throat covered in each frame).   
   
**Object segmentation (2D and 3D)**:   
  
Currently, I am developing a color base segmentation algorithm that detects the residue in the throat from recorded 2D endoscope     
videos. The color space I am using is HSV. The diagnostic approach to dysphagia is endoscopic swallow study. The patient swallows 
different consistencies of food (thin, puree, and hard). Puree and hard food are dyed in green, while thin is dyed in white. Using 
the color base segmentation, the algorithm is only able to detect one color at a time. In choosing to detect green, the algorithm 
produces data ratio of the green pixel values in the video to the entire throat captured in the video. This can easily be plotted to 
show the amount of residue in throat per each video frame.   
   
**Object Tracking (2D and 3D)**:  

I am currently looking into the different modes of object tracking. I found that Blob detection is one option, but ideally I want to 
fuse this algorithm with the object segmentation above.  
   
**Surface Area and Volume Quantification (3D)**:   
  
3D video and images will provide additional data that can be used to calculate the volume. The data is distance. The 3D stereoscopic 
cameras will provide the distance from the camera to the back of the throat, and the distance from the camera to the top of the 
residue. With the right scaling, the surface area can be calculated.  
To calculate volume, we would have to assign some coordinate system and do some math.  
   
In progress... This post will be continuously updated.

   
[Photo Credits](https://www.voicedoctor.net/diagnosis/voice/anatomy)
   
