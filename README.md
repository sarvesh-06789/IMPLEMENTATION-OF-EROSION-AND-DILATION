# IMPLEMENTATION-OF-EROSION-AND-DILATION
### NAME: SHARVESHWARAN M
### REG. NO: 212224240150
# Aim
To write a Python program using OpenCV to perform morphological operations—specifically Erosion and Dilation—on an image containing text.

# Algorithm
1. Import Required Libraries: Load OpenCV (cv2), NumPy (np), and Matplotlib (matplotlib.pyplot).
2. Create Input Image:Initialize a black canvas image of size $500 \times 500 \times 3$ with zeros (uint8).Add text (e.g., "Hello, I am Pugazhenthi S") onto the image using cv2.putText().
3. Display Input Image: Convert BGR to RGB and display the original image with text using Matplotlib.
4. Define Structuring Element (Kernel): Create a $3 \times 3$ array of ones as the structuring element (kernel = np.ones((3, 3), np.uint8)).
5. Perform Erosion:Apply cv2.erode() to shrink foreground text structures.Display the eroded image using Matplotlib.Perform Dilation:Apply cv2.dilate() to expand foreground text structures.
6. Display the dilated image using Matplotlib.

# Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# 1. Create a blank image and add text
image = np.zeros((500, 600, 3), dtype=np.uint8)
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Hello, I am SHARVESHWARAN M', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# 2. Display the original input image
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image with Text")
plt.axis('off')

# 3. Create a 3x3 structuring element (kernel)
kernel = np.ones((3, 3), np.uint8)

# 4. Apply Erosion
eroded_image = cv2.erode(image, kernel, iterations=1)

plt.subplot(1, 3, 2)
plt.imshow(cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB))
plt.title("Eroded Image")
plt.axis('off')

# 5. Apply Dilation
dilated_image = cv2.dilate(image, kernel, iterations=1)

plt.subplot(1, 3, 3)
plt.imshow(cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB))
plt.title("Dilated Image")
plt.axis('off')

plt.tight_layout()
plt.show()
```
# Output

<img width="922" height="867" alt="image" src="https://github.com/user-attachments/assets/991d4d5c-e6f8-4729-a67e-fcaa16073af9" />
<img width="1275" height="713" alt="image" src="https://github.com/user-attachments/assets/6ceb1eea-343a-4484-b469-f401774774e6" />
<img width="1276" height="867" alt="image" src="https://github.com/user-attachments/assets/fda5aa74-2b97-44e3-bb81-150b42f5335a" />
<img width="1102" height="801" alt="image" src="https://github.com/user-attachments/assets/dadf17c2-6843-4a93-bbe4-6f3c89b00bc8" />


# Result
The Python program to perform erosion and dilation on an image using OpenCV was successfully executed:

Erosion thinned the foreground text regions by reducing pixel boundaries.

Dilation thickened the foreground text regions by expanding pixel boundaries.
