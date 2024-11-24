# IMAGE-TRANSFORMATIONS





## Aim

To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.



## Software Required:

Anaconda - Python 3.7



## Algorithm:

### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization



### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.



### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:



Translation moves the image along the x or y-axis.Scaling resizes the image by scaling factors.Shearing distorts the image along one axis.Reflection flips the image horizontally or vertically.Rotation rotates the image by a given angle.



### Step4:

Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.



### Step5:

Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.



## Program:

### Developed By: K.R.HASHISH VIDYA SAGAR

### Register Number: 212222230047



```

import cv2

import numpy as np

import matplotlib.pyplot as plt



# Load the image

image = cv2.imread('car 2.jpeg')

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib



# Plot the original image

plt.figure(figsize=(7,3))

plt.imshow(image_rgb)

plt.title("Original Image")

plt.axis('off')

```

### Output

![Screenshot 2024-10-04 103558](https://github.com/user-attachments/assets/1a1280a2-999a-486d-9ada-115799110afc)





### i)Image Translation

```

rows, cols, _ = image.shape

M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels

translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))



plt.figure(figsize=(7,3))

plt.imshow(translated_image)

plt.title("Translated Image")

plt.axis('off')

```

### Output

![image](https://github.com/user-attachments/assets/55ed35d3-e3ca-46d4-9e0e-3d712b044cf8)



### ii) Image Scaling

```

scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x



plt.figure(figsize=(7,3))

plt.imshow(scaled_image)

plt.title("Scaled Image")

plt.axis('off')

```

### Output

![image](https://github.com/user-attachments/assets/81de56d2-e958-499c-adc4-cc079c5e3963)



### iii)Image shearing

```

M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5

sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))



plt.figure(figsize=(7,3))

plt.imshow(sheared_image)

plt.title("Sheared Image")

plt.axis('off')

```

### Output

![image](https://github.com/user-attachments/assets/e21b57dc-ee22-4598-a336-26b9867f7f43)





### iv)Image Reflection

```

reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)



plt.figure(figsize=(7,3))

plt.imshow(reflected_image)

plt.title("Reflected Image")

plt.axis('off')

```

### Output

![image](https://github.com/user-attachments/assets/7b295e93-6103-4b18-bf25-9f28473d5b9e)



### v)Image Rotation

```

M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 150, 1)  # Rotate by 150 degrees

rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))



plt.figure(figsize=(7,3))

plt.imshow(rotated_image)

plt.title("Rotated Image")

plt.axis('off')

```

### Output

![image](https://github.com/user-attachments/assets/f1fa02ac-1ff0-4829-acb9-1cb42c2e4a65)



### vi)Image Cropping

```

cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image



# Plot cropped image separately as its aspect ratio may be different

plt.figure(figsize=(7, 3))

plt.imshow(cropped_image)

plt.title("Cropped Image")

plt.axis('off')

plt.show()

```

### Output

![image](https://github.com/user-attachments/assets/a8a88cdd-6569-466c-8ad6-b7cb697854f4)
