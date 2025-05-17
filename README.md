# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
<br>


### Step2:
<br>
Import required libraries.


### Step3:
<br>
Create white noise image and use it to display the opening image.


### Step4:
<br>
Display the opening image.



### Step5:
<br>
Create black noise image and use it to display the closing image.



 
## Program:
```
# Import the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt


# Create the Text using cv2.putText
def load_img():
    blank_img=np.zeros((600,600))
    font=cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img,text='ABCDE',org=(50,300), fontFace=font, fontScale=5, color=(255,255,255), thickness=25, lineType=cv2.LINE_AA)
    return blank_img


# Create the structuring element
def display_img(img):
    fig=plt.figure(figsize=(12,10))
    ax=fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()


# Use Opening operation
white_noise=np.random.randint(low=0,high=2,size=(600,600))
white_noise=white_noise*255
noise_img=img+white_noise
opening=cv2.morphologyEx(noise_img,cv2.MORPH_OPEN,kernel)
display_img(opening)

# Use Closing Operation
black_noise=np.random.randint(low=0,high=2,size=(600,600))
black_noise=black_noise*-255
black_noise_img=img+black_noise
black_noise_img[black_noise_img==-255]=0
closing_image = cv2.morphologyEx(black_noise_img, cv2.MORPH_CLOSE, kernel)
display_img(closing_image)

```
## Output:

### Display the input Image
![image](https://github.com/user-attachments/assets/43c1c157-0861-4c2f-8e28-0960b83c8e9c)


### Display the result of Opening
![image](https://github.com/user-attachments/assets/1dce5de6-9ff9-465f-944a-7ae89dc6b8cf)

### Display the result of Closing
![image](https://github.com/user-attachments/assets/a83706c4-45cc-4ae9-bf19-f3c5c69f2f0c)


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
