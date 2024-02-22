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
### Developed By:SIVARAM R
### Register No:212222100050
## i) Write the frame as JPG file
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("siva.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## iii) Display the video by resizing the window
``` Python
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
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
``` Python
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
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![IMG-20240222-WA0005](https://github.com/sivaram-R/Image_Acqusition-_using_Web_Camera/assets/121165794/98676acf-96d2-487c-b647-75d9da1eb070)

### ii) Display the video

![IMG-20240222-WA0008](https://github.com/sivaram-R/Image_Acqusition-_using_Web_Camera/assets/121165794/966f6466-a3b8-4fa9-9e88-063c356fe8e7)

### iii) Display the video by resizing the window
![IMG-20240222-WA0006](https://github.com/sivaram-R/Image_Acqusition-_using_Web_Camera/assets/121165794/9f9e2235-c374-4bc0-a223-684e59c26c99)


### iv) Rotate and display the video

![IMG-20240222-WA0007](https://github.com/sivaram-R/Image_Acqusition-_using_Web_Camera/assets/121165794/8d2f7028-fd2f-4d52-a62a-db1d9f804e38)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
