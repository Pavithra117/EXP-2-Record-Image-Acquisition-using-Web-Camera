# EXP-2-Record-Image-Acquisition-using-Web-Camera

NAME: PAVITHRA K
REG NO: 212224240112

## Aim:
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file

2. Display the video

3. Display the video by resizing the window

4. Rotate and display the video


## Software Used:

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

## Algorithm:

Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

## Program:
```

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
## Output:
<img width="617" height="469" alt="image" src="https://github.com/user-attachments/assets/f50df4fc-0c99-4955-bb9d-a8f9aefeda26" />

<img width="635" height="447" alt="image" src="https://github.com/user-attachments/assets/1e5d17a1-cf0d-46b7-8482-60ce5fab0cb2" />

<img width="344" height="444" alt="image" src="https://github.com/user-attachments/assets/13e5fd06-beef-4631-83f3-a86f3763ab03" />

<img width="390" height="447" alt="image" src="https://github.com/user-attachments/assets/69772e6e-027b-4b64-a181-8172c66d1d02" />




## Result:
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
