# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program
### 1. Import the required libraries.
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```
### 2. Capture a frame from the webcam and save it as a JPG image.
```
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("dipt2.jpg", frame)

cap.release()
```
### 3. Read the captured image.
```
captured_image = cv2.imread("dipt2.jpg")
```
### 4. Display the captured image.
```
plt.imshow(captured_image[:, :, ::-1])
plt.title("Captured Frame")
plt.axis("off")
plt.show()
```
### 5. Display the live webcam video.
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
### 6. Display the video after resizing.
```
cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()
    time.sleep(0.05)

cap.release()
```
### 7. Rotate the video by 90° clockwise and display it.
```
cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

### Developed By:
**Name:** JANAGIRAMAN M

### Register No: 212224230101
---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`

<img width="647" height="512" alt="image" src="https://github.com/user-attachments/assets/1e6ff384-b4ce-412d-975d-557bb5322dba" />


### ii) Display the video
Live webcam video is displayed

<img width="645" height="477" alt="image" src="https://github.com/user-attachments/assets/5fcc84b9-e8dc-44a8-80aa-0bb8c13153ff" />

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

<img width="328" height="477" alt="image" src="https://github.com/user-attachments/assets/328fc040-94db-473b-8304-ebb8c1029429" />

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="357" height="471" alt="image" src="https://github.com/user-attachments/assets/18db7ab0-9650-4492-834d-dc34c2292286" />


---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
