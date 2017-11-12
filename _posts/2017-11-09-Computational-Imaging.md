---
layout: post
title: "User Interface for Computational Imaging"
author: "Napassorn Lerdsudwichai"
categories: resources
tags: [resources]
image:
  feature: led.jpg
---

## Project Description
In the [Computational Imaging System Laboratory](http://sites.bu.edu/tianlab/), this project aims to develop a computational microscopy system that synergistically combines optical hardware and computational software to improve resolution, information, and imaging capabilities of imaging microscopes. My overall objective is developing the computational layer of this project; specifically, the MATLAB graphical user interface (GUI) that implements various image-processing algorithms to achieve high-resolution quantitative images of nanoparticles and biological samples.  

## Project Significance
Nanoparticle microscopy has a wide range of applications. In medicine, nanoparticles are applied to cancer therapy (i.e. drug delivery, etc.), and cancer imaging or screening methods. In biology, nanoparticles are applied for virus capturization (i.e. virus size, distribution, shape, and orientation, etc.) and vesicle-cell research. As no traditional microscope is capable of seeing nanoparticles, computational microscopy for nanoparticle imaging is currently very demanding. The graphical user interface (GUI) I am continuing to develop provides the computational microscope with both essential and novel imaging capabilities without the requirements of configuring optical hardware (i.e. inserting numerous condenser aperture, polarization components, and/or specialized objectives) like in traditional microscopes. The GUI can improve resolution and imaging capabilities of optical systems, and become a user-friendly tool for researchers with no background in optics to conduct advanced image-processing computations. Ultimately, the progress made in this research can benefit not only the field of high-resolution microscopy, but also facilitate research breakthroughs in many fields.

## Methodology
My objective is to improve the robustness of the following GUI algorithms I have successfully implemented in the summer of 2017:  
1. **Image Inspection**: The algorithm conducts Fourier analysis and histogram equalization to deliver spatial frequency data, and make intensity uniform throughout the images. The GUI is currently compatible with a reflection-mode microscope and a scanning light source that generates a square grid of illumination angles. I aim to remove the GUI’s dependency on the square grid so that other light sources with non-square grid shapes can be used.  
2. **Image Manipulation**: This step applies differential phase contrast (DPC) and digital refocusing to the histogram equalized image set to yield a qualitative visualization of nanoparticles regardless of their positions on the image plane. DPC normalizes the intensities of each image that has an illumination numerical aperture (NA) within a NA bound specified by the user in the GUI. Digital refocusing sums up these intensities in each image to simulate images obtained from the microscope at different focal planes. In addition to removing square grid dependency in this step too, I aim to develop a dynamic code that selects an optimized NA bound closest to what the user inputs, as DPC cannot correctly normalize within all NA bounds.  
3. **Image Reconstruction**: This component uses the unweighted small perturbation (SPM) 2D deconvolution model to produce a high-resolution quantifiable image that describes the object’s height. My goal is to continue developing this component into the GUI and possibly combine alternative reconstruction options (weighted SPM deconvolution, Kirchhoff approximation-based deconvolution model), and developing dynamic code for calculating reconstruction parameters called Tikhonov’s regularizers.    

I also intend to expand the GUI’s compatibilities to other microscopic platforms such as transmission-mode microscopes. Lastly, train users to use my GUI and compile feedback to make the GUI more user-friendly.   

## Outcomes
Hence, from designing and refining this GUI, I hope to:
1. Produce a GUI that enhances nanotechnology research and improves virus detection.
2. Further improve my skills in graphical user interface design.
3. Gain rich knowledge about optical theory and imaging modalities.


[Photo Credits](https://www.idjnow.com/eliminator-led-array-powerful-rgb-led-derby-effect-light.html)
