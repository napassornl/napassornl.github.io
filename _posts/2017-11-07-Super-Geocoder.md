---
layout: post
title: "Super Geo-coder"
author: "Napassorn Lerdsudwichai"
categories: resources
tags: [resources]
image:
  feature: map.jpg
---

[**Super Geo-coder Github**](https://github.com/napassornl/Super-GeoCoder)

This is an automation application that allows the user to upload a file with a table format that stores a list of address to the browser and retrieve list of latitude and longitude coordinates of each address appended to the table.   

The user clicks the Submit button and the browser will display the table along with two new columns of the latitude and longitude corresponding to the address in each column. Then, the user is able to download this table as a .csv file to their local directory.  

Within the geopy library, I used the geocoder module to obtain the latitude and longitude coordinates. I used the Python pandas dataframe for storing the information. Then I wrote code that appended these coordinates to the excel sheet and made it available to be downloaded by the user.   

[Photo Credits](http://container-news.com/intra-asia-container-volumes-swell-7-2-sept-jiffa/)
