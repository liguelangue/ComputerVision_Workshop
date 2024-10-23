# Averaging/Box Filter
```
blurred_avg = cv2.blur(img, (5, 5))
```
Averaging is useful when you need basic noise reduction without caring much about edge preservation.

# Gaussian Blurring 
```
blurred_gauss = cv2.GaussianBlur(img, (5, 5), 0)
```
Gaussian Blurring is preferred when you need smoother results with better edge preservation.
Kernel size, must be odd (e.g., (5, 5))

# Median Blurring
```
blurred_median = cv2.medianBlur(img, 5)
```
Median Blurring works best for images with sharp noise, such as salt-and-pepper noise.
Kernel size, must be an odd number (e.g.5).

# Bilateral Filtering 
```
blurred_bilateral = cv2.bilateralFilter(img, 9, 75, 75)
```
Bilateral Filtering should be used when you need to reduce noise while preserving edges.
sigmaColor: Filter sigma in the color space (larger values blur more).
sigmaSpace: Filter sigma in the coordinate space (larger values mean more spatial smoothing).


# Comparision
1. When I implement these four methods on the same image "einstein.png", it shows that Gaussian Bluring performs better than the others.
Because for facial images, we need to preserve the edge to recognize the facial features and get a soomther image output.

2. Especially, I find an image with salt-and-pepper noise("noise2.png"). And when I implement median blurring and set the ksize to 7, most of the noise is removed.
