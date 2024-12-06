# Lab 10: Camera

## Overview
This workshop implements and compares two different optical flow techniques using OpenCV:
1. Lucas-Kanade Optical Flow (Sparse)
2. Dense Optical Flow (Farneback method)

## Implementation Details

### Features
- Real-time webcam capture with adjustable resolution
- Toggle between different visualization modes:
  - Original camera feed
  - Lucas-Kanade optical flow
  - Dense optical flow
- FPS (Frames Per Second) counter
- Interactive mode switching

### Controls
- Press 'l': Switch to Lucas-Kanade optical flow mode
- Press 'd': Switch to Dense optical flow mode
- Press 'q': Quit the application

## Technical Implementation

### Lucas-Kanade Optical Flow
- **Method**: Sparse optical flow using Shi-Tomasi corner detection
- **Parameters**:
  ```python
  feature_params = dict(
      maxCorners=50,      # Maximum number of corners to track
      qualityLevel=0.3,   # Minimum quality level
      minDistance=10,     # Minimum distance between corners
      blockSize=7         # Size of window for corner detection
  )
  ```
- **Visualization**: 
  - Green lines show motion paths
  - Red dots indicate current feature points

### Dense Optical Flow
- **Method**: Farneback algorithm
- **Parameters**:
  ```python
  cv2.calcOpticalFlowFarneback(
      prev_gray, curr_gray, None,
      0.5,  # Pyramid scale
      3,    # Pyramid levels
      15,   # Window size
      3,    # Iterations
      5,    # Poly_n
      1.2,  # Poly_sigma
      0     # Flags
  )
  ```
- **Visualization**: 
  - Color represents motion direction
  - Intensity represents motion magnitude

## Observations and Analysis

### Performance Comparison
1. **Lucas-Kanade Method**
   - Advantages:
     - Computationally efficient
     - Good for tracking specific features
     - Clear visualization of motion paths
   - Limitations:
     - Only tracks sparse features
     - Can lose tracking points in rapid motion

2. **Dense Optical Flow**
   - Advantages:
     - Provides full motion field
     - Better for analyzing overall motion patterns
   - Limitations:
     - More computationally intensive
     - Can be sensitive to noise

## Additional Implementation: FPS Implementation and Analysis

### Technical Implementation
```python
# FPS calculation variables
prev_frame_time = 0
new_frame_time = 0

# Inside the main loop
new_frame_time = time.time()
fps = 1/(new_frame_time-prev_frame_time) if prev_frame_time > 0 else 0
prev_frame_time = new_frame_time
fps_text = f"FPS: {int(fps)}"

# Display FPS on frame
cv2.putText(output, fps_text, (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 
           1, (0, 255, 0), 2)
```

