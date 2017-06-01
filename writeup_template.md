# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road

[//]: # (Image References)

[image1]: ./test_images_output/grey_solidWhiteCurve.jpg "Grayscale"
[image2]: ./test_images_output/blurred_solidWhiteCurve.jpg "Blurred"
[image3]: ./test_images_output/cannied_solidWhiteCurve.jpg "Edge detected"
[image4]: ./test_images_output/region_solidWhiteCurve.jpg "Region selected"
[image5]: ./test_images_output/houghed_solidWhiteCurve.jpg "Hough space"
[image6]: ./test_images_output/solidWhiteCurve.jpg "Final Lane Enhanced"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps and final process image 1 steps so the total has 6 steps

First, I converted the images to grayscale, 

Second, Smoothing the grayscale images using Gaussion kernel,

Third, Edge detection using Cannied algorithm.

Fourth, Select the region of the lane.

Fifth, Convert the edges within the region of interests into lane lines using hough space transform.

Sixth, Finally extend lines got from step 5 to fill to the bottom of the image and upper bound. 

![Grey][image1]
![Blurred][image2]
![Cannied][image3]
![Region Selected][image4]
![Lane Detected][image5]
![Lane Enhanced][image6]


### 2. Identify potential shortcomings with your current pipeline


The left and right lines are drawn by just finding top and bottom points and drew a straight line. so all the points between are not being used in current logic.

Another problem is in the step 6 i am extending the lines to top and bottom of the image.The method of extending to the bootom and top is just by calculating two points from based on the stop of the existing lines, so it may not be on the actual lane.




### 3. Suggest possible improvements to your pipeline

It can be improved by considering all the points between the top and bottom.
And also the line extension should consider whether the slopes of the originally detected are changing wildly or not.

