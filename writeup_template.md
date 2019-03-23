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



### 2. Identify potential shortcomings with your current pipeline

1. This function wouldn't work for curve since it uses only linear line-fitting.
2. When the lane mark of the next lane was detected, it would classifyed to the one of the classes and the lane detection is disturbed 
3. Robustness against blur lane mark.
4. Robustness against image contrast. (e.g. Nithgt)


### 3. Suggest possible improvements to your pipeline

A possible improvement for each shortcomings would 
1. After the filtering, convert the image to top view, and fit the line with Clothoid or curve. It would be better if ROI changes depends on the steering angle.
2. Optimize ROI. If we need to detect ego lane's line narrow ROI would work.
3. If no lane mark detected in current frame, we can predict the lane by using previous frame
4. This would be difficult to solove by the pipeline. We need to use other type of camera filter like RCCB.
