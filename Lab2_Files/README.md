# Loading images with OpenCV
```
img = cv2.imread("flower.png")
```
Using the cv2 python library

The imread function loads an image
```
gray_img = cv2.imread("flower.png", cv2.IMREAD_GRAYSCALE)
```
cv2.IMREAD_GRAYSCALE specifies to load an image in grayscale mode

# Displaying images with OpenCV
```
cv2.imshow("flower image", img)
 ```
Method to display an image in a window
```
cv2.waitKey(0)
```
Allows users to display a window for given milliseconds or until any key is pressed
```
cv2.destroyAllWindows()
```
Allows users to destroy or close all windows at any time after exiting the script

The cv2.waitkey(0) command and cv2.destroyAllImages command will close the pop-up once any key is presse.

To display the grayscale image:
```
cv2.imshow("flower gray scale image", gray_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.waitKey(1)
```
# Saving images with OpenCV
```
cv2.imwrite("lab_2_image.png", gray_img)
```
filename: A string representing the file name

image: the image that is to be saved
