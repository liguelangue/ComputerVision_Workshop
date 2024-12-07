# Simple Thresholding Example
Simple Thresholding: a fixed threshold value is used for theentire image. Each pixel value is compared to this threshold value and the pixel is assigned a binary value.
```
_, thresh_simple = cv2.threshold(image, 127, 255, cv2.THRESH_BINARY)
```
127: The threshold value.
255: The value to be given to pixels exceeding the threshold.
cv2.THRESH_BINARY: The type of thresholding to be applied (e.g.,cv2.THRESH_BINARY, cv2.THRESH_BINARY_INV, etc.).

# Adaptive Thresholding Example
Two main types of adaptive thresholding:

• Mean Adaptive Thresholding: threshold is set to be the mean of the neighborhood values minus a constant

• Gaussian Adaptive Thresholding: threshold is set as the weighted sum of the neighborhood values minus a constant
```
# Apply adaptive mean thresholding
thresh_adaptive_mean = cv2.adaptiveThreshold(image, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2)
# Apply adaptive Gaussian thresholding
thresh_adaptive_gaussian = cv2.adaptiveThreshold(image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```
255: The value to be given to the pixels that exceed the threshold.
cv2.ADAPTIVE_THRESH_MEAN_C/cv2.ADAPTIVE_THRESH_GAUSSIAN_C: The method for calculating the threshold.
thresholdType: The type of thresholding to apply(e.g., cv2.THRESH_BINARY).
blockSize: Size of the neighborhood area used to calculate the threshold for each pixel (must be an odd number).

# Otsu’s Binarization Example
Otsu’s Binarization: automatically calculates the optimal threshold value based on the image’s histogram
```
# Apply Otsu’s binarization
_, thresh_otsu = cv2.threshold(image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
thresh: Set to 0 because Otsu’s method, automatically determines the optimal threshold.
maxval: The maximum value to assign to thresholded pixels.
type: The thresholding method (e.g.cv2.THRESH_BINARY) combined with cv2.THRESH_OTSU for automatic threshold determination

# Additional Implementation:

## Change Test Image

Not only test the given photo.png, but I also test the other image in the folder.

## Change Parameters

Try to use different block size to adaptive mean thresholding, and compare the results.

Try to use different block size to adaptive Gaussian thresholding, and compare the results.

