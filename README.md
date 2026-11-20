# Record-Image-Acquisition-using-Web-Camera
EX 02: Image_Acqusition-_using_Web_Camera Aim: To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG

ii) Display the video

iii) Display the video by resizing the window

iv) Rotate and display the video

Software Used: Anaconda - Python 3.7

Algorithm: Step 1: Use cv2.VideoCapture(0) to access web camera.

Step 2: Use cv2.imread to read the video or image.

Step 3: Use cv2.imwrite to save the image.

Step 4: Use cv2.imshow to show the video.

Step 5: End the program and close the output video window by pressing 'q'.

Program:

Developed By: DEEPIKA V

Register No: 212224240030

## i) Write the frame as JPG file
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
cap = cv2.VideoCapture(0)

if not cap.isOpened():
    print("Error: Webcam not detected")
else:
    print("Webcam connected successfully")
```
image

<img width="624" height="415" alt="image" src="https://github.com/user-attachments/assets/0a80ed0a-4689-4a30-a76f-4a3d6e30c1b7" />


ii) Display the video
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
import time
from IPython.display import clear_output

# Open webcam
cap = cv2.VideoCapture(0)

if not cap.isOpened():
    print("Webcam not detected")

else:
    print("Webcam connected successfully")

    for i in range(50):

        ret, frame = cap.read()

        if not ret:
            print("Image capture failed")
            break

        # Convert BGR to RGB
        frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

        # Display webcam image
        clear_output(wait=True)
        plt.imshow(frame_rgb)
        plt.axis('off')
        plt.title("Webcam Image Acquisition")
        plt.show()

        time.sleep(0.05)

    # Release webcam
    cap.release()
    print("Webcam released successfully")

```

<img width="640" height="432" alt="image" src="https://github.com/user-attachments/assets/db51f538-79f5-4f90-9540-a5210762a14c" />


iii) Display the video by resizing the window
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
import time
from IPython.display import clear_output

cap = cv2.VideoCapture(0)

for i in range(50):

    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)

    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

<img width="402" height="395" alt="image" src="https://github.com/user-attachments/assets/0605bd12-c351-4a38-845f-8d679b14d585" />



iv) Rotate and display the video
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

if not cap.isOpened():
    print("Camera not detected!")
else:
    print("Camera started successfully")

    for i in range(50):
        ret, frame = cap.read()

        if not ret:
            print("Cannot read frame")
            break

        rotated_frame = cv2.rotate(
            frame, cv2.ROTATE_90_CLOCKWISE
        )

        frame_rgb = cv2.cvtColor(
            rotated_frame, cv2.COLOR_BGR2RGB
        )

        clear_output(wait=True)
        plt.figure(figsize=(5, 5))
        plt.imshow(frame_rgb)
        plt.title("Rotated Video")
        plt.axis('off')
        plt.show()
        plt.close()

        time.sleep(0.05)

    cap.release()
    print("Camera released")
```


<img width="340" height="432" alt="image" src="https://github.com/user-attachments/assets/177c587e-1da0-43a5-a4c9-24c7deef1d9a" />


Result: Thus the image is accessed from webcamera and displayed using openCV.
