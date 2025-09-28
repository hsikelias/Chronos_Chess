# THE PLAN

- The first thing to start with is the __board detection__. Try out differnet opencv techniques like **edge detection**, **Hough transforms**, and **X-corner identifiction**. But these are not advanced, need much modern machine learning stuff(need to do more research).


## CLASSIC CV METHODS FOR BOARD DETECTION:

### 1. Edge Detection and Contour Finding
1. Goal: Identify the four precise pixel coordinates of the chessboard's corners by identifying its outer boundary
2. Process:
       - Image converted to greyscale
       - A **Sobel operator**, a type of matrix convolution, is applied to calculate the gradient at each pixel, highlighting edges where pixel values change rapidly
       - The **Canny operator** refines these gradients into a binary image showing only edge pixels
       - The algorithm then finds contours (continuous lines of edge pixels) and looks for a large quadrilateral shape that could be the board's outline
3. Pros and Cons: This method is extremely fast but requires very clean images. It fails easily if the board's outline is obstructed by pieces, hands, shadows, or other objects

### 2.Tile Contour with Warping and Scoring
1. Goal: To find the board by first identifying a single tile and then reconstructing the board from it, making the process more robust to obstructions
2. Process:
       -  Instead of the whole board, the algorithm looks for contours that could be individual tiles
       -  For each potential tile contour, it warps the edge image so the tile becomes a perfect square
       -  Then "scores" this warped image by counting the number of edges along the expected locations of the chessboard's grid lines
       -  This process is repeated for many different contours and all 64 possible tile positions on the board
       - This method is quite robust but computationally very expensive due to the massive search space. It can take up to several minutes to process a single            image
   
   
