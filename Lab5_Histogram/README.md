# Grayscale Histogram Implementation
```
hist = cv2.calcHist([img], [0], None, [256], [0, 256])
```
• cv2.calcHist(): This OpenCV function computes the histogram of an image.
• [img]: The input image, which is passed as a list because OpenCV expects the image data in this format.
• [0]: The index of the channel for which the histogram is calculated. Since the image is grayscale, there's only one channel (0).
• None: This is where a mask would go if you wanted to calculate the histogram for only a specific region of the image. Here, we use the entire image, so no mask is needed.
• [256]: This represents the number of bins. Since the intensity values of the grayscale image range from 0 to 255, we use 256 bins to represent all possible values.
• [0, 256]: The range of pixel values we want to consider (0 to 255).

Then, plot the histogram using Matplotlib.

# Color Histogram Implementation
Three separate histograms, one for each color channel (Blue, Green, Red).

Loop through each color channel (Blue, Green, Red):
1. Calculate the histogram for each channel
2. Plot the histogram for the current channel
