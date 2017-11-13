---
layout: post
title: "User Interface for Computational Imaging"
author: "Napassorn Lerdsudwichai"
categories: resources
tags: [resources]
image:
  feature: led.jpg
---

## About
The [Computational Imaging System Laboratory](http://sites.bu.edu/tianlab/) is developing a computational microscopy system that synergistically combines optical hardware and computational software to improve resolution, information, and imaging capabilities of imaging microscopes.   

My contribution is in the development of the computational layer of this project; specifically with the Matlab **G**raphical **U**ser **I**nterface (GUI) that implements various image-processing algorithms to achieve high-resolution quantitative images of nanoparticles and biological samples (ie. viruses).  

## Why a Computational Software?
Computational Imaging is a very complex field in Computer Engineering. However, as I explained in one of my [posts]({{ site.github.url }}{% post_url 2017-10-13-Computational-Imaging %}}), the information obtained from it is invaluable. It provides traditional microscopes with novel imaging capabilities without the requirement of configuring optical hardware. We thus get super-resolution and quantifiable iamges with just lines of code. How cool is that! But what if someone who is not currently an expert in the field wants to do some computational imaging? Should that person attempt to obtain a Ph.D degree in computational imaging first? Well, whatever that person wants to do, he/she'll have to wait 5-6 years.  

That is where a user interface for computational imaging comes in. Its user friendliness and intuitive interactions allows non-expert users from researchers in other fields of science to undergraduates to conduct convoluted computations and image processing by just clicking some buttons. Now, anyone can view some cool images from those complex algorithms and get exposure to the field. They will definitely become just as fascinated as I am with the power of computational imaging.  

## Why nanoparticle microscopy?
First off, we can't see nanoparticles with our naked eye. To help with scaling, you can see blood and blood consists of red blood cells. We can see the liquid state of blood, but we can't see the solid red blood cells. Red blood cells are ~7 microns; that is ten to the sixth smaller than a meter. Nanoparticles are ten to the ninth smaller. So, we definitely cannot see nanoparticles let alone do research on them. So why do we even want to study them?  

Nanoparticle research has a wide range of applications. Examining nanoparticles under a microscope (hence, nanoparticle microscopy) in medicine can lead to curing cancer (i.e. through cancer drug delivery). In biology, nanoparticles are applied in virus capturization. In other words, virus, which are just the same size as nanoparticles, can now be assessed with nanoparticle research. Critical information to understand the life cycle of a virus such as, virus size, distribution, shape, and orientation can be extracted. Thus, we further enhance the development of virus detection and prevention. This is very relevant as we recently had a virus epidemic (the Zika virus) back in early 2015. There are many more real-world applications that can be achieved with nanoparticle research, but I believe you are now convinced that nanoparticle microscopy is crucial.   

## The Approach  
These are some current functions that my GUI can do:  

### Image Inspection   
This set of computational algorithms conduct **Fourier Transform analysis** and **histogram equalization**.   

#### Fourier Transform
The Fourier Transform simply allows us to extract more data from images. We are transforming data in the time domain into the frequency domain, getting the spatial frequencies from images. With this information, we can understand many useful things in an image most importantly, detail. We can also manipulate the Fourier Transforms so that we extract detail from an image. We can see how details in an image change or depend on certain frequencies.   

#### Histogram Equalization
When taking a random picture, we get an image that is brighter on one side than the other. This is because the intensity or brightness of the image is not uniform. The intensity distribution in an image is called the image histogram. Thus, as its name states histogram equalization ensure to make the intensity uniform throughout an image. This is important for further image processing in computational imaging.     

### Image Manipulation   
This algorithm applies **digital refocusing** and **differential phase contrast (DPC)** to the histogram equalized images to yield a high-resolution, qualitative visualization of nanoparticles.   

#### Digital Refocusing  
You may recall when looking under a microscope, we had to turn some knob on the side of the microscope in order to make the object under examination "in focus". This is exactly what digital refocusing does, but since the images are already taken, there is no knob for us to turn. We have to do this "digitally". Digital refocusing is an algorithm that simulates the "knob turning". In more technical terms, it simulates changing the depth of the focal plane, where the depth here is referring to the distance between the microscope and the object under examination.  

#### Differential Phase Contrast (DPC)  
DPC normalizes the intensities of each image that has an illumination numerical aperture (NA) within a NA bound specified by the user in the GUI. In traditional microscopes, there is a certain angle range that is exposed to light. This is known as the NA. But remember, we already took the images so the user must specify this angle range of NA bound for us. Thus, DPC elimates noise from images that would otherwise prevent us from getting the extra desired details from images.

Hence, with these two methods, we are able to get high-resolution, qualitative images. It's qualitative because we are able to digitally change the focusing knob or digital refocus the image so that we can see any object in the image in focus. It has high resolution because we eliminated most of the noise or unwanted data from the images.      

### Image Reconstruction  
The images captured from the microscope are 2D, but by capturing the same image with different lighting or at different illumination angles, we can reconstruct the 2D image to produce a 3D image. How awesome is that! But we can do better, we can produce a 3D high-resolution quantifiable image! We can extract the exact height of a nanoparticle. This technique uses the unweighted small perturbation (SPM) 2D deconvolution model for reconstruction. My goal is to continue developing this component into the GUI and possibly combine alternative reconstruction options such as, the weighted SPM deconvolution, and Kirchhoff approximation-based deconvolution model.    

## Next Steps
The GUI is currently compatible with a reflection-mode microscope and a scanning light source that generates a square grid of illumination angles. I aim to remove this dependency on the square grid so that other light sources with non-square grid shapes like circles can be used. I also intend to expand the GUI’s compatibilities to other microscopic platforms such as transmission-mode microscopes. Lastly, I am training users to use my GUI and compile their feedback to make the GUI more user-friendly.     

## Outcomes
Hence, from designing and refining this GUI, I have realized the power of computational imaging. From a tiny nanoparticle that was invisible to the naked eye, computational imaging allows us to not only see it, but study it under high resolution. Super fancy! I am very grateful to be part of this project as I not only gained rich knowledge about optical theory and digital imaging processing, but I also got to further improve my skills in graphical user interface design.  


[Photo Credits](https://www.idjnow.com/eliminator-led-array-powerful-rgb-led-derby-effect-light.html)
