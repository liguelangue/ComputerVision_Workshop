# Averaging/Box Filter
Averaging is useful when you need basic noise reduction without caring much about edge preservation.

# Gaussian Blurring 
Gaussian Blurring is preferred when you need smoother results with better edge preservation.

# Median Blurring
Median Blurring works best for images with sharp noise, such as salt-and-pepper noise.

# Bilateral Filtering 
Bilateral Filtering should be used when you need to reduce noise while preserving edges.

When I implement these four methods on the same image "einstein.png", it shows that Gaussian Bluring performs better than the others.
Because for facial images, we need to preserve the edge to recognize the facial features and get a soomther image output.
