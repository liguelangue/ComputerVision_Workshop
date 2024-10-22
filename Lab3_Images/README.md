# Resizing Images
```
resized_img = cv2.resize(img, (500, 500))
```
img: Input image

(500, 500): Size  of the output image, (width, height)
# Cropping Images
```
cropped_img = img[80:280, 150:330]
```
First dimension is always the number of rows and heights of the image

Second dimension is the number of columns or the width of the image
# Rotating Images
```
rotated_img = cv2.rotate(img, cv2.ROTATE_90_CLOCKWISE)
```
To rotate clockwise by 90 degrees: cv2.ROTATE_90_CLOCKWISE

To rotate counter-clockwise by 90 degrees: cv2.ROTATE_90_COUNTERCLOCKWISE

To rotate clockwise by 180 degrees: Cv2.ROTATE_180
# Image Colors Spaces and Conversions
```
gray_img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
hsv_img = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
Grayscale is a color space where each pixel value represents the intensity of light. Instead of having multiple color channels (like RGB), a grayscale image has only one channel, which contains shades of gray ranging from black to white.

HSV is a cylindrical color space that describes colors in terms of three components:
• Hue (H): The color type, represented as a degree on the color wheel (0-360°). In OpenCV, it's scaled to 0-179.
• Saturation (S): The intensity or purity of the color (0-255).
• Value (V): The brightness or lightness of the color (0-255).
HSV is used in color filtering, object tracking, and image segmentation
# Drawing Shapes and Text
```
# Drawing a line
line_img = cv2.line(line_img, (80, 150), (280, 330), (0,0,0), 10)

# Drawing a rectangle
rectangle_img = cv2.rectangle(rectangle_img, (100, 150), (250, 330), (0,0,0), 10)

# Drawing a circle
circle_img = cv2.circle(circle_img, (200, 300), 50, (0, 0, 0), 10)

# Putting a text
text_img = cv2.putText(text_img, 'Xinmeng Wu', (100, 300), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 5)
```
cv2.line(image, (x1, y1), (x2, y2), (color), thickness)
• (x1, y1) are the starting coordinates of the line
• (x2, y2) are the ending coordinates of the line
• Color is the color of the line to be drawn in RGB
• Thickness is the thickness of the line in px

cv2.rectangle(image, (x1, y1), (x2, y2), (color), thickness)
• (x1, y1) is the starting coordinate
• (x2, y2) is the ending coordinate
• (color) is color in RGB
• Thickness in thickness in px

cv2.circle(image, (center x, center y), radius, (color), thickness)
• (center x, center y) is the center coordinate of the circle

cv2.putText(image, ‘text’, (x, y), font, fontScale, (color), thickness)
• (x, y) is the coordinate of the bottom-left corner of the text string in the image
• Font denotes the font type. (e.g. FONT_HERSHEY_SIMPLEX, FONT_HERSHEY_PLAIN)
• FontScale is a font scale factor that is multiplied by the font specific base size
• Color is the color of text string to be drawn in RGB
• Thickness if the thickness of the line in px




