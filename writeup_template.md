# **Finding Lane Lines on the Road** 

## Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 4 steps. 

Firstly, I converted the image to grayscale. I then ran canny on the grayscale image to 
produce edge-detected image. I followed this by running a hough transform on the canny
ouput to detect lines which followed the strongest gradient. And, lastly, I applied an 
image mask to focus only on the region of the image I was interested in.

Regarding the draw_lines() function - I initially tried using the cv2.fitline() function
to find the parameters for the best fit line - which worked. However extrapolating did not
work [I'm still looking into this]. To draw a thicker outline, however, I ended up increasing
the thickness of the lines in the original function.


### 2. Identify potential shortcomings with your current pipeline


The main shortcoming in my current pipeline is the flawed extrapolation. 


### 3. Suggest possible improvements to your pipeline

A possible (and currently being researched) improvement - is implementing a better method for calculating the ends of the currently drawn lines.
