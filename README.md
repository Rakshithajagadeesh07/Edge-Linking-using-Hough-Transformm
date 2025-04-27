# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

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

## Program :

### Name: Rakshitha J
### Reg No: 212223240135
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('fz.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')

```
## Output:

### Input image :

![download](https://github.com/user-attachments/assets/a5a2d5ea-c9a5-4457-b1fe-bd8774bc9a71)

### Grayscale image :

![download](https://github.com/user-attachments/assets/f198eab7-cef5-478e-99a8-006b22d53ce9)

### Canny Edge detector output :

![download](https://github.com/user-attachments/assets/c10ee75b-f0a2-4efc-a279-02b1aafa6ca5)

### Display the result of Hough transform :

![download](https://github.com/user-attachments/assets/37d652b6-b53e-4a4e-b3b5-7b2d16834c74)

## Result:

Thus the grayscale image , canny edge detector and hence we had displayed the result of hough transform
