# face_mesh_drawing

Tracks a face from a webcam feed with MediaPipe Face Mesh and draws the mesh over it with OpenCV.

## What it does

- Opens a webcam stream and runs MediaPipe Face Mesh on each frame
- Draws the face mesh tessellation onto the live image
- Collects landmark pixel coordinates (`[id, x, y]`) for each frame
- Displays the FPS on screen
- `face_mesh_utils.py` contains a small `detector` class that can also be set to `hands` or `pose`

## Tech

Python, OpenCV, MediaPipe (legacy `mp.solutions` API), NumPy

## Running it

```bash
pip install opencv-python mediapipe numpy
python face_mesh_ex.py
```

Notes:
- The script opens camera index `1` (`cv2.VideoCapture(1)`). If you only have one webcam, change it to `0`.
- `Face_videos/` contains sample clips, but the default script uses the webcam; pass a file path to `cv2.VideoCapture` to use one instead.
- Run `face_mesh_ex.py`, not `face_mesh_utils.py` directly (the latter's `main()` uses a mode the class doesn't support).
- Written in 2021 against an older MediaPipe release.

This was an early learning project for getting familiar with MediaPipe and OpenCV.
