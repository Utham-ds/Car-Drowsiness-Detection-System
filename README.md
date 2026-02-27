# Car Drowsiness Detection

A Python-based real-time driver drowsiness detection script that monitors eye aspect ratio (EAR) using facial landmarks and raises an audible alert when prolonged eye closure is detected.[web:195][web:201]

## Requirements

- This project currently works **only with Python 3.7**.
- Other Python versions (3.8+) are **not supported** and may fail because of dependency issues (especially `dlib`).[web:171][web:201]
- A working webcam.

## Tech Stack

- Python 3.7
- OpenCV (`cv2`) for video capture and image processing[web:195]
- dlib for face detection and 68-point facial landmarks[web:195][web:203]
- imutils for convenience functions (resizing, landmark helpers)[web:195]
- SciPy (`scipy.spatial.distance`) for Euclidean distance calculation[web:195]
- winsound (Windows) for beep alerts

## How It Works

- Captures frames from the webcam in real time.
- Uses dlib’s frontal face detector and 68-point shape predictor (`shape_predictor_68_face_landmarks.dat`) to locate facial landmarks.[web:195][web:203]
- Extracts the coordinates of the left and right eye regions.
- Computes the Eye Aspect Ratio (EAR) for each eye using vertical and horizontal landmark distances.[web:195][web:198]
- Averages both eyes’ EAR and compares it to a threshold (`earThresh`).
- If the EAR stays below the threshold for a set number of consecutive frames (`earFrames`), it:
  - Displays “DROWSINESS DETECTED” on the frame.
  - Plays a beep sound using `winsound.Beep`.

## Project Structure

```text
Car_drowsiness_detection.py       # Main script
shape_predictor_68_face_landmarks.dat  # Dlib facial landmark model (not included, download separately)
README.md                         # Project documentation
```
## Author

Utham Kumar Mohanlal
