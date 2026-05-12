# Detect-the-lines-using-Hough-Transform

## Aim

To implement lane detection using OpenCV by applying grayscale conversion, Canny edge detection, and Hough Line Transform techniques on an input image.

---

## Learning Objective

* Understand image preprocessing techniques
* Learn edge detection using the Canny operator
* Understand line detection using Hough Transform
* Visualize detected lines on the original image

**Important Instruction:**  
👉 Execute the program step-by-step  
👉 Do NOT modify the logic unnecessarily

---

## Software Used

* Anaconda – Python 3.x
* Jupyter Notebook / VS Code
* OpenCV (`cv2`)
* NumPy
* Matplotlib

---

## Developed By

* **Name:** _____________S V SHADHANASHREE_______________
* **Register No:** ___212223230202___________________

## Algorithm & Explanation

---

### Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

These libraries are used for image processing, mathematical operations, and displaying images.

---

### Step 2: Read the Image

```python
# Load the image using OpenCV
image = cv2.imread('Qn_7_.jpg')
```

Reads the input image from the specified file path.

---

### Step 3: Convert to Grayscale

```python
# Convert image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

Converts the color image into grayscale to simplify processing.

---

### Step 4: Display Images

```python
# Display original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

# Display grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

Displays both the original and grayscale images.

---

### Step 5: Edge Detection using Canny Operator

```python
# Detect edges using Canny Edge Detector
edges = cv2.Canny(gray_image, 50, 150)
```

Detects edges in the grayscale image using threshold values 50 and 150.

---

### Step 6: Display Edge Detected Image

```python
# Display edge detected image
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

Displays the edges detected in the image.

---

### Step 7: Hough Line Transform

```python
# Detect lines using Hough Transform
lines = cv2.HoughLinesP(
    edges,
    1,
    np.pi / 180,
    100,
    minLineLength=50,
    maxLineGap=10
)
```

Detects straight lines from the edge-detected image.

---

### Step 8: Draw Detected Lines

```python
# Draw detected lines on original image
for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```

Draws the detected lines on the original image using green color.

---

### Step 9: Display Final Output

```python
# Display final image with detected lines
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```

Displays the final output image with detected lane lines.

---

## Expected Output

* Original image
  
<img width="515" height="388" alt="image" src="https://github.com/user-attachments/assets/fb3f0306-70a5-4dd7-9453-2a1785d33975" />

* Grayscale image

<img width="515" height="388" alt="image" src="https://github.com/user-attachments/assets/97d663d0-cc8f-422f-b2c7-12a11132dc1e" />

  
* Edge detected image

  <img width="515" height="388" alt="image" src="https://github.com/user-attachments/assets/95cba202-b019-4dc3-8bb2-179bf1181dff" />

* Image with detected lines using Hough Transform

  <img width="515" height="388" alt="image" src="https://github.com/user-attachments/assets/7a800b4f-691a-4026-ba24-6e65d99b067f" />



---

---

## Result

Thus, lane detection using Canny Edge Detection and Hough Line Transform is successfully implemented using OpenCV.

---

