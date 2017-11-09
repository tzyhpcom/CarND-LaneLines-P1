ne Lines on the Road** 

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

I define a function named lane_line_pipeline() to present the pipeline. It consists of 6 step.
1. converted the images to grayscale.
2. execute gaussian blur on gray image.
3. select interest region, which have lane lines in it.
4. use hough transform to detect line segments, then split segments to left or right lane line according to it's position and slope, finally calculate left/right linear parameters and draw two lines on a whole empty map. I implemented it with function hough_lines_lane(), which combine original hough_lines() and draw_lines().
5. select interest region on the image we got from step 4.
6. combine original image and the image we got from step 6.

The whole pipeline is demonstrated in lane_line_pipeline(), and it shows some pictures in P1.ipynb and P1.html.

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be there would be lots of detected hough lines which are not belong to lane lines when the road is not clean and flat. 

Another shortcoming could be the region is fixed in select region step, which is not much robust. 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to mainly check the region the lane line mostly appear, which may be two triangles on left and right of the image.

Another potential improvement could be to use some image processing steps to enhancement lane lines.

