# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step-1:
Create a black image of size 100x600 pixels.
### Step-2:
Use a specified font to write the word "Lifestyle" on the image at a defined position.
### Step-3:
Show the image containing the text without axis labels.
### Step-4:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).
### Step-5:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.
### Step-6:
Apply dilation to the original image using the same structuring element to increase the size of white regions.
 
## Program:
```
Developed By: SRINIDHI SENTIL 
Reg.No: 212222230148
```
``` Python
# Import the necessary packages
import numpy as np
import cv2
import matplotlib.pyplot as plt

# Create the Text using cv2.putText
img = np.zeros((100, 600, 3), dtype='uint8')  # Black background (RGB: 0, 0, 0)
font = cv2.FONT_HERSHEY_COMPLEX
text_color = (255, 255, 255)  # White text (RGB: 255, 255, 255)
cv2.putText(img, 'SRINIDHI', (60, 70), font, 2, text_color, 5, cv2.LINE_AA)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/1d5bb371-13d3-4814-8b39-86d3aaa84559)


```
# Create the structuring element
kernel = np.ones((5,5),np.uint8)
kernel1 = cv2.getStructuringElement(cv2.MORPH_CROSS,(5,5))
cv2.erode(img,kernel)
```

![image](https://github.com/user-attachments/assets/c1905638-51d7-4898-adf9-e8b006811a78)
![image](https://github.com/user-attachments/assets/6e2a3fb7-181d-4a68-b633-c9e680afacef)


```
# Erode the image

img_erode = cv2.erode(img,kernel1)
plt.imshow(img_erode)
plt.axis('off')
```
### Display the Eroded Image

![image](https://github.com/user-attachments/assets/3fe35c94-7d30-408f-a396-0720ca04b9b1)

```
# Dilate the image
img_dilate = cv2.dilate(img,kernel1)
plt.imshow(img_dilate)
plt.axis('off')

```
### Display the Dilated Image
![image](https://github.com/user-attachments/assets/533eb5d9-5c5b-4b3b-bebc-5eec9fc321ee)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
