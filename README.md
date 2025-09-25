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

![WhatsApp Image 2025-09-25 at 22 46 32_2fd1d640](https://github.com/user-attachments/assets/d123962b-3950-42b9-924a-df9460422fd5)


### ii) Display the video

![WhatsApp Image 2025-09-25 at 22 46 47_4ed5637f](https://github.com/user-attachments/assets/56ac084a-8f22-4b76-b19f-96a593b06c34)


### iii) Display the video by resizing the window

![WhatsApp Image 2025-09-25 at 22 47 00_4c09193c](https://github.com/user-attachments/assets/f2a0af7e-ddc4-4961-bcbe-a345fabcef87)


### iv) Rotate and display the video


![WhatsApp Image 2025-09-25 at 22 47 14_2498c412](https://github.com/user-attachments/assets/18221499-a698-4650-8d9e-56ed447c88fc)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
