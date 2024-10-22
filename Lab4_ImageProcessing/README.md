# Implementing Keypoint Detection - HCD
I use HCD to implement keypoint detection on two images: flower.png and seal.png.
```
harris_corners = cv2.cornerHarris(gray_hcd, blockSize=20, ksize=3, k=0.04)
```
• blockSize – neighborhood size
• ksize – aperture parameter for Sobel() operator
• freeParameter – harris detector free parameter
```
harris_corners = cv2.dilate(harris_corners, None)
```
Dilates an image by using a specific structuring element that determines the shape of a pixel neighborhood which the maximum is taken.

# Implementing Keypoint Detection - SIFT
```
sift = cv2.SIFT_create()
keypoints, descriptors = sift.detectAndCompute(gray_img, None)
```
detect the keypoints of the flower.png using SIFT
```
image_with_keypoints = cv2.drawKeypoints(img, keypoints, None, flags = cv2.DRAW_MATCHES_FLAGS_DRAW_RICH_KEYPOINTS)
```
draw the keypoints on the original image
# Feature Matching with FLANN
1. Apply SIFT to detect key points for both images
2. Use FLANN Matcher
    ```
    FLANN_INDEX_KDTREE = 1
    index_params = dict(algorithm=FLANN_INDEX_KDTREE, trees=5)
    search_params = dict(checks=50)
    flann = cv2.FlannBasedMatcher(index_params, search_params)
    matches = flann.knnMatch(descriptors1, descriptors2, k=2)
    ```
    FLANN_INDEX_KDTREE: Algorithm for indexing, using KD-tree.
    index_params: Specifies the algorithm and number of trees.
    search_params: Controls the number of checks during the search.
    knnMatch( ): Performs K-Nearest Neighbor matching between the descriptors of the two images. It returns the k best matches for each descriptor.
3. Draw good matches.



