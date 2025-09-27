# THE PLAN

- The first thing to start with is the __board detection__. Try out differnet opencv techniques like **edge detection**, **Hough transforms**, and **X-corner identifiction**. But these are not advanced, need much modern machine learning stuff(need to do more research).


## CLASSIC CV METHODS FOR BOARD DETECTION:

### 1. Edge Detection and Contour Finding
1. Goal: Identify the four precise pixel coordinates of the chessboard's corners by identifying its outer boundary
2. Process:
       - Image converted to greyscale
       - A **Sobel operator**, a type of matrix convolution, is applied to calculate the gradient at each pixel, highlighting edges where pixel values change rapidly
       - The **Canny operator** refines these gradients into a binary image showing only edge pixels
   
