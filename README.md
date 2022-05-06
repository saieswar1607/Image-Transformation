# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import the necessary libraries and read the original image and save it as a image variable.
<br>

### Step2:

Translate the image using M=np.float32([[1,0,20],[0,1,50],[0,0,1]]) translated_img=cv2.warpPerspective(input_img,M,(cols,rows))
<br>

### Step3:

Scale the image using M=np.float32([[1.5,0,0],[0,2,0],[0,0,1]]) scaled_img=cv2.warpPerspective(input_img,M,(cols,rows))
<br>

### Step4:

Shear the image using M_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]]) sheared_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))
<br>

### Step5:

Reflection of image can be achieved through the code M_x=np.float32([[1,0,0],[0,-1,rows],[0,0,1]]) reflected_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))
<br>

### Step6:

Rotate the image using angle=np.radians(45) M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]]) rotated_img=cv2.warpPerspective(input_img,M,(cols,rows))
<br>

### Step7:

Crop the image using cropped_img=input_img[20:150,60:230]
<br>

### Step8:

Display all the Transformed images and end the program.
<br>

## Program:
```python
Developed By: Sai Eswar Kandukuri
Register Number: 212221240020
i)Image Translation

import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("gray.jpeg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
M= np.float32([[1, 0, 100],
                [0, 1, 200],
                 [0, 0, 1]])
translatedImage =cv2.warpPerspective (inputImage, M, (cols, rows))
plt.imshow(translatedImage)
plt.show()

ii) Image Scaling

import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("gray.jpeg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
M = np. float32 ([[1.5, 0 ,0],
                 [0, 1.8, 0],
                  [0, 0, 1]])
scaledImage=cv2.warpPerspective(inputImage, M, (cols * 2, rows * 2))
plt.imshow(scaledImage)
plt.show()

iii)Image shearing

import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("gray.jpeg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
matrixX = np.float32([[1, 0.5, 0],
                      [0, 1 ,0],
                      [0, 0, 1]])

matrixY = np.float32([[1, 0, 0],
                      [0.5, 1, 0],
                      [0, 0, 1]])
shearedXaxis = cv2.warpPerspective (inputImage, matrixX, (int(cols * 1.5), int (rows * 1.5)))
shearedYaxis = cv2.warpPerspective (inputImage, matrixY, (int (cols * 1.5), int (rows * 1.5)))
plt.imshow(shearedXaxis)
plt.show()
plt.imshow(shearedYaxis)
plt.show()

iv)Image Reflection

import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("gray.jpeg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
matrixx=np.float32([[1, 0, 0],
                    [0,-1,rows],
                    [0,0,1]])
matrixy=np.float32([[-1, 0, cols],
                    [0,1,0],
                    [0,0,1]])
reflectedX=cv2.warpPerspective(inputImage, matrixx, (cols, rows))
reflectedY=cv2.warpPerspective(inputImage, matrixy, (cols, rows))
plt.imshow(reflectedY)
plt.show()

v)Image Rotation

import numpy as np
import cv2
angle=np.radians(45)
inputImage=cv2.imread("gray.jpeg")
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotatedImage = cv2.warpPerspective(inputImage,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotatedImage)
plt.show()

vi)Image Cropping

import numpy as np
import cv2
import matplotlib.pyplot as plt
angle=np.radians(45)
inputImage=cv2.imread("gray.jpeg")
CroppedImage= inputImage[20:150, 60:230]
plt.axis('off')
plt.imshow(CroppedImage)
plt.show()

```
## Output:
### i)Image Translation
<br>
<img width="284" alt="exp5_1" src="https://user-images.githubusercontent.com/93427011/166984080-187dde77-2dd9-46ac-8dd2-05f166639f7a.png">
<br>

### ii) Image Scaling
<br>
<img width="284" alt="exp5_2" src="https://user-images.githubusercontent.com/93427011/166984140-ce6a4b1b-a0cc-4197-b1c2-093e7f6335ab.png">
<br>

### iii)Image shearing
<br>
<img width="215" alt="exp5_3" src="https://user-images.githubusercontent.com/93427011/166984174-15c56640-b384-48a4-a56a-999bc3dcfaaf.png">
<br>

### iv)Image Reflection
<br>
<img width="288" alt="exp5_4" src="https://user-images.githubusercontent.com/93427011/166984202-bd6fc682-859c-4fc5-a061-49657cddfd8b.png">
<br>

### v)Image Rotation
<br>
<img width="254" alt="exp5_5" src="https://user-images.githubusercontent.com/93427011/166984250-0f383633-ffcc-432b-b7a6-ad70a3205c65.png">
<br>

### vi)Image Cropping
<br>
<img width="344" alt="exp5_6" src="https://user-images.githubusercontent.com/93427011/166984283-4c166d09-26bd-4bb5-a8a0-b5dc78a0d683.png">
<br>

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
