# **Finding Lane Lines on the Road** 

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

My pipeline consisted of 5 steps. 
1. Convert the images to grayscale.
2. Apply Gaussian noise kernel
3. Apply Canny transform
4. Apply image-masking to clip ROI
5. Draw lane lines. Here I modified the draw_lines() function as follows.
  a. Calcurate hough lines from the processed image
  b. Classify the line(start point and end point) to two classes depends on each slopes. Left-lane and right-lane.
  c. Fit lines for each list of points
6. Return the image with lines

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

a. This function wouldn't work for curve since it uses only linear lines.
b. When the lane mark of the next lane was detected, it would classifyed to the one of the classes and the lane detection is disturbed 
c. Robustness against blur lane mark.
d. Robustness against image contrast. (e.g. Nithgt)
e. It wouldn


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
