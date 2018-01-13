# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

1. I convert the image to grayscale to avoid any distortions resulting from color.

2. I apply a Gaussian Blur to fill possible gaps and smooth the edges.

3. I apply the Canny Edge Detection Algorithm to find edges in the images, because edges are a great starting point to find lane markings.

4. I set a region of interest, where i would expect the lanes

5. I use the Hough transformation to find Lines within the detected edges

6. I detect the min and max values in X and Y-Dimensions of the detected lines

7. I interpolate from the min and max values to the borders of my region of interest and put a line through it


![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One shortcoming is the way the lane lines are marked. Lanes are marked as straight lines and therefore there is no curvature there. If the car doesnt drive in a straight line the detection will fail.

Another shortcoming is that the lines tend to flicker because of insufficient quality of detected lines.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to detect curvatures to more accurately draw the lanes.

Another possible improvement would be to average the values over some timeframe to get a more smoothed out result.
