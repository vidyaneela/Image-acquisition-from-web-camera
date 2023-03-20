# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
Write the captured image using cv2.imwrite("pic.jpg",frame)

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

### Step 4:
Display the image until the loop gets over.

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).

## Program:
``` 
### Developed By: Vidya Neela M
### Register No: 212221230120

## i) Write the frame as JPG file
import pandas as pd
import cv2
import numpy as np
cam = cv2.VideoCapture(0)
while(True):
    ret,frame = cam.read()
    cv2.imwrite("pic.jpg",frame)
    result = False
cam.release()
cv2.destroyAllWindows()

## ii) Display the video
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imshow('image',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window
cap = cv2.VideoCapture (0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int (cap.get(4)) 
    image = np.zeros(frame. shape, np. uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image [height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import numpy as np
import cv2
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image

![image](https://user-images.githubusercontent.com/94169318/226411768-c074a676-5afe-4c63-b31b-9dbcb0f17747.png)


### ii) Display the video

![image](https://user-images.githubusercontent.com/94169318/226412034-8fee781d-485d-41bd-a639-8c0cc645324b.png)


### iii) Display the video by resizing the window

![image](https://user-images.githubusercontent.com/94169318/226412313-a24aa37c-b83a-4d0e-9cec-25246fff5b25.png)


### iv) Rotate and display the video

![image](https://user-images.githubusercontent.com/94169318/226412635-f1031b7c-d518-4f1d-9b3a-7d3edb898600.png)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
