The counting and classifying program has been divided into 2 separate codes. However, both codes are similar with a few lines of code being deleted or commented out to specify each program function. The count program must be watched until the end of the video output to get the desired results. You can cut the video short by pressing Q. The program did not use any existing classifying object and tree packages such as deepforest. 

The code uses the contour detection method from the OpenCV library. The contour detection function cv2.findContours returns all the contours in the image. The contours are used to approximate the shape of the trees.

The function is_tree takes an image and a contour as inputs and returns a boolean value. It first calculates the bounding rectangle of the contour and the area of the contour. Then, it checks if the area of the contour is above a certain threshold compared to the expected area of a tree. If the ratio is above the threshold, the function returns True, indicating that the contour is likely a tree. Otherwise, it returns False.

The function count_unique_trees takes an image and a list of contours as inputs. It iterates over each contour in the list and checks if it is a tree using the is_tree function. If it is a tree, the function uses the contour area as a unique tree ID and adds it to a set of tree IDs. The function finally returns the number of unique tree IDs, which represents the number of unique trees detected in the image.

The code reads each frame of the video, converts it to grayscale, and applies a threshold to create a binary image. It then finds all the contours in the binary image and counts the number of unique trees in each frame. The count is incremented in a loop, and the count is further divided by 30 since 1 second has 30 frames. The final count represents the total number of unique trees detected in the video.

The use of contours in this code provides a simple and efficient way to detect and count trees in a video. However, it should be noted that the code assumes that each tree has a unique shape and size, which may not be the case in real-world scenarios. Additionally, the contour-based approach may not be very accurate for detecting trees with overlapping or partially occluded branches.



