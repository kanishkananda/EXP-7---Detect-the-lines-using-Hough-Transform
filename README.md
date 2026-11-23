# EXP:7 - Detect-the-lines-using-Hough-Transform

# NAME: N.KANISHKA
# REGISTER NO: 212225230127

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---

###  Step 1: Import Libraries
###  Step 2: Load the image using imread() from cv2 module
###  Step 3: Convert the image to grayscale
###  Step 4: Using Canny operator from cv2, detect the edges of the image
###  Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
###  Step 6: Draw the detected lines on the original image
### Display the result of Hough Transform (Image with lines)

---
## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('kanish1.jpg')
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
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"

# Step 6: Draw the detected lines on the original image

for line in lines:
    x1, y1, x2, y2 = line  # Unpacking coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

## Output

<img width="357" height="487" alt="image" src="https://github.com/user-attachments/assets/b8f99a3a-199a-4ed9-8aee-083ff7df5657" />

<img width="357" height="486" alt="image" src="https://github.com/user-attachments/assets/2cfeba07-e0f9-400f-b73f-8378e8df252e" />

<img width="358" height="492" alt="image" src="https://github.com/user-attachments/assets/08ab915c-1272-4554-bb66-c96858118cc0" />

<img width="361" height="487" alt="image" src="https://github.com/user-attachments/assets/82474278-29bc-48a7-9b93-f93cf247d6e3" />


## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.
