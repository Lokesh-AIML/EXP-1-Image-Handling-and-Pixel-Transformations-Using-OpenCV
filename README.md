# EXP-1-Image-Handling-and-Pixel-Transformations-Using-OpenCV

# AIM:
Write a Python program using OpenCV that performs the following tasks:

Read and Display an Image.
Adjust the brightness of an image.
Modify the image contrast.
Generate a third image using bitwise operations.
Software Required:
Anaconda - Python 3.7
Jupyter Notebook (for interactive development and execution)
# Algorithm:
# Step 1:
Load an image from your local directory and display it.

# Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

# Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.
Display the original, brighter, and darker images.

# Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).
Display the original, lower contrast, and higher contrast images.

# Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

# Program Developed By:
# Name: Lokeshwaran S
# Register Number: 212224240080

1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```
img_gray = cv2.imread(r'C:\Users\waran\Eagle_in_Flight.jpg', 0)
print(img_gray)
```
[[144 145 146 ... 101 103 102]

 [146 147 145 ...  99  98  99]
 
 [148 145 144 ...  99  94  96]
 
 ...
 
 [121 124 122 ... 127 130 136]
 
 [127 133 136 ... 130 127 119]
 
 [127 132 136 ... 117 116 111]]
 
2. Print the image width, height & Channel.
```
height, width = img_gray.shape
print("Width :", width)
print("Height :", height)
print("Channel : 1")
```
3. Display the image using matplotlib imshow().
```
```
4. Save the image as a PNG file using OpenCV imwrite().
```
```
5. Read the saved image above as a color image using cv2.cvtColor().
```
```
6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```
```
7. Crop the image to extract any specific (Eagle alone) object from the image.
```
```
8. Resize the image up by a factor of 2x.
```
```
9. Flip the cropped/resized image horizontally.
```
```
10. Read in the image ('Apollo-11-launch.jpg').
```
```
11. Add the following text to the dark area at the bottom of the image (centered on the image):
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN
```
```
12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
rect_color = magenta
```
```
13. Display the final annotated image.
```
```
14. Read the image ('Boy.jpg').
```
```
15. Adjust the brightness of the image.
```
```
16. Create brighter and darker images.
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
```
```
17. Display the images (Original Image, Darker Image, Brighter Image).
```
```
18. Modify the image contrast.
```
```
19. Display the images (Original, Lower Contrast, Higher Contrast).
```
```
20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```
```
21. Merged the R, G, B , displays along with the original image
```
```
22. Split the image into the H, S, V components & Display the channels.
```
```
23. Merged the H, S, V, displays along with original image.
```
```
Output:
i) Read and Display an Image.
ii) Adjust Image Brightness.
iii) Modify Image Contrast.
iv) Generate Third Image Using Bitwise Operations.
Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
