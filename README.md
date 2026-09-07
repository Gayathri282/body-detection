# Body State Detector

Standalone browser prototype using webcam + MediaPipe Pose Landmarker.

## Run
Because browsers restrict webcam access on ordinary `file://` pages, serve this folder from a local HTTP server.

### Python
```bash
python -m http.server 8000
```
Then open:
http://localhost:8000

### What it detects
- IDLE — LEFT / CENTER / RIGHT
- JUMPING — LEFT / CENTER / RIGHT
- SQUATTING — LEFT / CENTER / RIGHT
- NO PERSON

The camera preview is deliberately small and the rest of the UI is black.

## Notes
The prototype uses body landmarks rather than a 3×3 camera grid. Horizontal position is divided into thirds. Jumping and squatting use landmark geometry and short temporal smoothing, which is more reliable than simply checking whether the person occupies the top/middle/bottom of the camera.
