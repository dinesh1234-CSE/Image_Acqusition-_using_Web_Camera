# Image_Acqusition-_using_Web_Camera
## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:
``` Python
### Developed By: CH.V.SIVA DINESH KUMAR
### Register No: 212224040055
```

## i) Write the frame as JPG file
```Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
ret,frame = videoCaptureObject.read()
cv2.imshow('DAP',frame)
if cv2.waitKey(1) == ord('q'):
break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
ret,frame = videoCaptureObject.read()
cv2.imshow('DAP',frame)
if cv2.waitKey(1) == ord('q'):
break
videoCaptureObject.release()
cv2.destroyAllWindows()

```
## iii) Display the video by resizing the window
```Python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
ret, frame = cap.read()
width = int(cap.get(3))
height = int(cap.get(4))
image = np.zeros(frame.shape, np.uint8)
smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
image[:height//2, :width//2] = smaller_frame
image[height//2:, :width//2] = smaller_frame
image[:height//2, width//2:] = smaller_frame
image [height//2:, width//2:] = smaller_frame
cv2.imshow('DAP', image)
if cv2.waitKey(1) == ord('q'):
break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```Python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
ret, frame = cap.read()
width = int(cap.get(3))
height = int(cap.get(4))
image = np.zeros(frame.shape, np.uint8)
smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[:height//2, width//2:] = smaller_frame
image [height//2:, width//2:] = smaller_frame
cv2.imshow('DAP', image)
if cv2.waitKey(1) == ord('q'):
break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image

![webcam_img (1)](https://github.com/user-attachments/assets/35ac482d-7720-4997-bd15-2917fe480fd4)



### ii) Display the video



![webcam_img (1)](https://github.com/user-attachments/assets/98b9cb80-d426-415e-b7fd-b857f772a840)


### iii) Display the video by resizing the window


![captured_image1](https://github.com/user-attachments/assets/98dd79da-6a63-4f13-9039-b32d47ad8e05)



### iv) Rotate and display the video


![captured_image2](https://github.com/user-attachments/assets/7e8061b4-68f3-4576-b2e2-d106f9eb6037)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
