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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied a Gaussian blur and Canny edge detection.I used low_threshold = 50 and high_threshold = 150. 
Then a mask to the image outputted by Canny image detection and finally filter the lines found by the Hough Transform.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by color and thickness.

If you'd like to include images to show how the pipeline works, here is how to include an image: 
    img = cv2.imread('test_images/'+file_name)
    img=pipeline(img)
    cv2.imwrite(output_directory+file_name, img)
![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when lines are curves or sharp turns. 
Another shortcoming could be road signs and other objects a lot of cars on the road.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use information from the previous frame when detecting lanes in the current frame.
Another potential improvement could be to use a nonlinear curve to the lanes.
