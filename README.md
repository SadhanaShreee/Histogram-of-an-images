# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().

### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: SADHANA SHREE B
# Register Number: 212223230177

import cv2
import matplotlib.pyplot as plt

# Load and check the image
image = cv2.imread("Eagle.png")
if image is None:
    print("Image not found!")
    exit()

# Convert to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Show original grayscale image
plt.imshow(gray, cmap='gray')
plt.title("Original Grayscale Image")
plt.axis('off')
plt.show()

# Plot histogram of original image
hist_gray = cv2.calcHist([gray], [0], None, [256], [0, 256])
plt.plot(hist_gray, color='black')
plt.title("Original Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.grid(True)
plt.show()

# Apply histogram equalization
equalized = cv2.equalizeHist(gray)

# Show equalized image
plt.imshow(equalized, cmap='gray')
plt.title("Equalized Image")
plt.axis('off')
plt.show()

# Plot histogram after equalization
hist_eq = cv2.calcHist([equalized], [0], None, [256], [0, 256])
plt.plot(hist_eq, color='black')
plt.title("Equalized Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.grid(True)
plt.show()

```
## Output:
### Input Grayscale Image and Color Image
![Screenshot 2025-05-21 192645](https://github.com/user-attachments/assets/40f3a155-6f0f-4ef9-baa6-21baa55f8fcd)


### Histogram of Grayscale Image and any channel of Color Image
![Screenshot 2025-05-21 192653](https://github.com/user-attachments/assets/7d66d18f-2827-4f81-a109-ec132cff89d9)



### Histogram Equalization of Grayscale Image.

![Screenshot 2025-05-21 192713](https://github.com/user-attachments/assets/ac52fc98-434f-4a04-b0f0-c65227bf5caf)



## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
