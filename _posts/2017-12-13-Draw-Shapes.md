---
layout: post
title: "Simple Drawing Program for Windows Desktop"
author: "Napassorn Lerdsudwichai"
categories: resources
tags: [resources]
image:
  feature: abstract.jpg
---

Download the Program [here.](https://github.com/napassornl/Draw-Shapes)  

Note: The program was created as a Windows Form Application using C#.NET and so can only be used on a Windows OS.

# High Level Program Description
In this Windows Application form, I used object-oriented programming for the different shapes that the user can draw on the panel of the form. Specifically, each shape (line, rectangle, and ellipse) is inherited from a base class that I created called myGraphics. The base class myGraphics has common data fields for all shapes (e.g. location coordinates from the mouse clicks). To draw on the panel, a paint event has to be called in the form. The myGraphics class has a Draw method that is called by the paint event of the main form. I then utilized polymorphism by overriding the base Draw method to each of the shape classes so that it customizes the Draw method for each shape.  

# How to Draw  
This is a simple drawing program that allows users to draw lines, rectangles, and/or ellipses. The user chooses what shape to draw in the draw panel.  

The user draws the shape with two mouse clicks on the white panel. The two mouse clicks set the invisible boundaries of the box containing the object. The user can click on any two opposite corners of the box, not just upper left and lower right.  

The user can specify the details of each shape by clicking the Settings Button, which will open a dialog box. The user can specify the width and color of the line or border of the rectangle and ellipse. Also, for rectangle and ellipse shapes, the user can adjust the fill color by checking the fill checkbox and choosing a fill color as shown:   

![Alt]({{ site.github.url }}/assets/img/setting.PNG)


# How to Edit and Save
The menustrip on the top bar of the window allows the user to undo his/her drawing or clear the drawing panel entirely.  

The user can also save his/ her work by selecting the Save tab. The user can save in many formats such as Jpeg, Png, Tiff, and Gif.  

Here is an example of a simple (but not as pretty) drawing saved as a Jpeg file from the program:  

![Alt]({{ site.github.url }}/assets/img/drawing.jpg)

Feel free to download the executable file [here](https://github.com/napassornl/Draw-Shapes)  and give it a try! 

[Photo Credits](http://hdqwalls.com/wallpapers/abstract-colorful-shape-lines.jpg)


