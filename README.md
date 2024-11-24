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

image = cv2.imread('Qn4.jpg')

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib



# Plot the original image

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 

```

### Output

![image](https://github.com/user-attachments/assets/6e205e83-3db0-430c-948f-f432e14a9360)

### i)Image Translation

```
tx, ty = 100, 50
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
```
```
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('off')


```

### Output

![image](https://github.com/user-attachments/assets/d64cca57-dcf9-4e76-82a5-25b161de8a9c)


### ii) Image Scaling

```
fx, fy = 5.0, 2.0
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
```
```
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')
```

### Output
![image](https://github.com/user-attachments/assets/84ba93b3-7638-4419-8d27-6535bc643b27)

### iii)Image shearing

```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')
```

### Output
![image](https://github.com/user-attachments/assets/5df8d616-5027-4a09-9241-2516e475fe0d)


### iv)Image Reflection

```
reflected_image = cv2.flip(image, 2) 
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')
```

### Output

![image](https://github.com/user-attachments/assets/8d25089f-ff9c-4e01-8607-8744867db20c)

### v)Image Rotation

```

(height, width) = image.shape[:2]
angle = 45
center = (width // 2, height // 2)
M_rotation = cv2.getRotationMatrix2D(center, angle, 1
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')

```

### Output
![image](https://github.com/user-attachments/assets/0cd0c5a4-d77c-4814-8da9-862dc9ee8e3d)

### vi)Image Cropping

```

x, y, w, h = 100, 100, 200, 150
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")
plt.axis('off')

```

### Output

![image](https://github.com/user-attachments/assets/6c7981f4-4dc8-4637-b2ce-41c92c88366d)

### Result:
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
