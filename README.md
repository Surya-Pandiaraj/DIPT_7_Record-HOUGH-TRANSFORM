### NAME: SURYA P <br>
### REG NO: 212224230280 <br> 
### Date: 20/11/2026

## EX. No. 7 : RECORD HOUGH TRANSFORM

##  Aim:

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective:

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

---

##  Software Used:

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---
## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## ProgramL
##  Developed By

* **Name:** Surya P
* **Register No:** 212224230280

### Input image and grayscale image:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('surya.jpg')  # Replace 'image.jpg' with your image path
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```
<img width="688" height="563" alt="image" src="https://github.com/user-attachments/assets/5a1946ae-49e8-4314-81d9-21a0aa2bf61a" />

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
<img width="683" height="562" alt="image" src="https://github.com/user-attachments/assets/88fe5d3a-8666-4a1f-ba13-48fd0501c93d" />


### Canny Edge detector output:
```
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
<img width="687" height="567" alt="image" src="https://github.com/user-attachments/assets/bf0d752b-9ad1-4e1a-9821-808e08eca3cf" />



### Display the result of Hough transform:
```
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
# Step 6: Draw the detected lines on the original image
if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line  # Unpack coordinates directly
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')

```
<img width="682" height="561" alt="image" src="https://github.com/user-attachments/assets/27af48f1-9f90-4419-ad8d-052dde4b1e3a" />


---

## Result :

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
