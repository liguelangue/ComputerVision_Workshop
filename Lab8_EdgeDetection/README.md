# Edge Detection Implementation

## Overview
This workshop implements and compares different edge detection techniques using OpenCV:
1. Sobel Edge Detection (with different kernel sizes)
2. Canny Edge Detection

## Implementation Details

### Sobel Edge Detection
- **Horizontal Edges (Sobel X)**
  ```python
  sobel_x = cv2.Sobel(image, cv2.CV_64F, 1, 0, ksize=3)
  ```
- **Vertical Edges (Sobel Y)**
  ```python
  sobel_y = cv2.Sobel(image, cv2.CV_64F, 0, 1, ksize=3)
  ```
- **Combined Edges**
  ```python
  sobel_combined = cv2.sqrt(sobel_x**2 + sobel_y**2)
  ```

### Canny Edge Detection
- First threshold: 100
- Second threshold: 200
- Provides cleaner edge detection with less noise

## Results Analysis

### Sobel Edge Detection
1. **Horizontal Edges (Sobel X)**
   - Effectively detects vertical changes in intensity
   - Highlights horizontal edges in the image

2. **Vertical Edges (Sobel Y)**
   - Detects horizontal changes in intensity
   - Highlights vertical edges in the image

3. **Combined Edges**
   - Provides complete edge information
   - Shows both horizontal and vertical edges

### Canny Edge Detection
- Produces cleaner edge maps
- Better at handling noise
- Results in thinner edges compared to Sobel

## Visualization
- All results are displayed using Matplotlib
- Original images and edge detection results are shown side by side
- Subplots are used for easy comparison of different techniques

## Additional Implementations

### Kernel Size Comparison in Sobel Edge Detection
I implemented different kernel sizes (3x3 and 5x5) in Sobel edge detection to compare their effects:

```python
# ksize = 3
sobel_x = cv2.Sobel(image, cv2.CV_64F, 1, 0, ksize=3)
sobel_y = cv2.Sobel(image, cv2.CV_64F, 0, 1, ksize=3)

# ksize = 5
sobel_x = cv2.Sobel(image, cv2.CV_64F, 1, 0, ksize=5)
sobel_y = cv2.Sobel(image, cv2.CV_64F, 0, 1, ksize=5)
```

#### Observations:
1. **3x3 Kernel**
   - Better at detecting fine details and textures
   - More sensitive to noise
   - Produces sharper edges

2. **5x5 Kernel**
   - Not working well on sample image
