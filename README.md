# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:

# Step-1:
Create a black image of size 100x600 pixels.

# Step-2:
Use a specified font to write the word "Lifestyle" on the image at a defined position.

# Step-3:
Show the image containing the text without axis labels.

# Step-4:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).

# Step-5:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.

# Step-6:
Apply dilation to the original image using the same structuring element to increase the size of white regions.
 
## Program:


# Import the necessary packages

```
import numpy as np
import cv2
import matplotlib.pyplot as plt
```

# Create the Text using cv2.putText

```
img = np.zeros((100, 600, 3), dtype='uint8') 
font = cv2.FONT_HERSHEY_COMPLEX
text_color = (255, 255, 255)  
cv2.putText(img, 'PRIYA VARSHINI', (60, 70), font, 2, text_color, 5, cv2.LINE_AA)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.axis('off')
plt.show()
```

# Create the structuring element

```
kernel = np.ones((5,5),np.uint8)
kernel1 = cv2.getStructuringElement(cv2.MORPH_CROSS,(5,5))
cv2.erode(img,kernel)

kernel = np.ones((3, 3), np.uint8)
```

# Erode the image

```
img_erode = cv2.erode(img,kernel1)
plt.imshow(img_erode)
plt.axis('off')
```


# Dilate the image

```
img_dilate = cv2.dilate(img,kernel1)
plt.imshow(img_dilate)
plt.axis('off')
```



## Output:

### Display the input Image

<img width="317" height="61" alt="image" src="https://github.com/user-attachments/assets/c533632b-e0fb-4c49-8f47-d000f1e54c59" />



### Display the Eroded Image

<img width="323" height="61" alt="image" src="https://github.com/user-attachments/assets/e1001794-5051-4d7c-821b-03d02387ff06" />



### Display the Dilated Image

<img width="316" height="56" alt="image" src="https://github.com/user-attachments/assets/61ac92de-55a5-40d8-b055-3f4aff648b8e" />


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
