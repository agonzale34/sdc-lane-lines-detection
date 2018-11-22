**Finding Lane Lines on the Road** 
---

### - My pipeline.

My pipeline consisted of 6 steps. 

#### 1.  Pre-process the input image:

First, I converted the images to gray scale using a filter with yellow mask to get better line contrast, then I reduce the noise in the image by applying gaussian blur algorithm 

#### 2. Find edges in the processed image:
Before to be able to detect lane lines is important to find edges in the image, to achieve this I used the canny transformation algorithm.

#### 3. Select the region of interest and eliminate anything else
for a better lane lines detection we only consider the edges inside a four-side polygon that specify where the lane lines are suppose to be.
I use the dimension of the image to calculate the vertices of polygon.

I block out all the edges that outside the polygon using the function fillPoly of OpenCV library.

#### 4. Get lines from the edges:
To get lines from the edges I use the Hough transformation algorithm, these lines are the key de identify the lane lines.

#### 5. Identify the lane lines: 
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by 
first grouping the lines using the angle (negative for left and positive for right), then I average the slope and intercept of each lines to get the equation of the line: y = mx + b,
I calculate the initial y final points for the final lane line using the equation


#### 6. Overlay the original image with the final lines
at the end of the pipeline I return the overlap image.


## Test images



![alt text][image1]


### - Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### - Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
