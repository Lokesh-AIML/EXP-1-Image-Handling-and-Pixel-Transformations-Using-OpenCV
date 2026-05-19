# EXP-1-Image-Handling-and-Pixel-Transformations-Using-OpenCV

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** Lokeshwaran S
- **Register Number:** 212224240080

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python
img_gray = cv2.imread(r'C:\Users\waran\Eagle_in_Flight.jpg', 0)
print(img_gray)
```

<img width="122" height="65" alt="image" src="https://github.com/user-attachments/assets/4d519a49-92d1-4699-8ff9-ea759d095ebd" />

#### 2. Print the image width, height & Channel.
```python
height, width = img_gray.shape
print("Width :", width)
print("Height :", height)
print("Channel : 1")
```

<img width="52" height="32" alt="image" src="https://github.com/user-attachments/assets/47a69374-90b9-463e-aac8-6932b1d9287c" />



#### 3. Display the image using matplotlib imshow().
```python
plt.imshow(img_gray, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```
<img width="254" height="206" alt="image" src="https://github.com/user-attachments/assets/19abc437-b131-47e4-be8f-c73a40d4d76d" />



#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
cv2.imwrite('eagle_output.png', img_gray)
print("Image Saved")
```

<img width="44" height="17" alt="image" src="https://github.com/user-attachments/assets/2d04bb23-8040-4e46-907b-9ec50030b72b" />


#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
img = cv2.imread('eagle_output.png')
img_color = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```



#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
plt.imshow(img_color)
plt.title('Color Image')
plt.axis('off')
plt.show()

height, width, channel = img_color.shape
print("Width :", width)
print("Height :", height)
print("Channels :", channel)
```

<img width="265" height="239" alt="image" src="https://github.com/user-attachments/assets/533b5389-bf56-4d2e-9c69-bc0c457ac96e" />


#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
crop_img = img_color[100:400, 150:500]

plt.imshow(crop_img)
plt.title('Cropped Eagle')
plt.axis('off')
plt.show()
```

<img width="232" height="215" alt="image" src="https://github.com/user-attachments/assets/608eaad4-f27d-46bd-8c71-144670e4914b" />


#### 8. Resize the image up by a factor of 2x.
```python
resized_img = cv2.resize(crop_img, None, fx=2, fy=2)

plt.imshow(resized_img)
plt.title('Resized Image')
plt.axis('off')
plt.show()
```

<img width="249" height="222" alt="image" src="https://github.com/user-attachments/assets/beb6f9d5-ee7e-411f-b2fc-6bb29d34fd40" />


#### 9. Flip the cropped/resized image horizontally.
```python
flipped_img = cv2.flip(resized_img, 1)

plt.imshow(flipped_img)
plt.title('Horizontally Flipped Image')
plt.axis('off')
plt.show()
```

<img width="229" height="209" alt="image" src="https://github.com/user-attachments/assets/bd5abd58-5bce-4f44-ab6a-4ff46397052a" />


#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
apollo_img = cv2.imread(r'C:\Users\waran\Apollo-11-launch.jpg')
apollo_img = cv2.cvtColor(apollo_img, cv2.COLOR_BGR2RGB)

plt.imshow(apollo_img)
plt.title('Apollo Launch')
plt.axis('off')
plt.show()
```

<img width="260" height="165" alt="image" src="https://github.com/user-attachments/assets/65bffc62-1cac-44e7-b972-b909a1542b3b" />


#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN

cv2.putText(apollo_img, text, (80, 550), font_face, 2, (255,255,255), 2)

plt.imshow(apollo_img)
plt.axis('off')
plt.show()
```

<img width="258" height="148" alt="image" src="https://github.com/user-attachments/assets/2eb3563d-3d63-4f41-87e0-1c9bbffcc1ca" />


#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = (255, 0, 255)

cv2.rectangle(apollo_img, (180, 50), (350, 500), rect_color, 3)

plt.imshow(apollo_img)
plt.axis('off')
plt.show()
```

<img width="255" height="144" alt="image" src="https://github.com/user-attachments/assets/8187e3c9-7bb8-4310-882e-9084e305f193" />


#### 13. Display the final annotated image.
```python
plt.figure(figsize=(8,8))
plt.imshow(apollo_img)
plt.title('Final Annotated Image')
plt.axis('off')
plt.show()
```

<img width="317" height="197" alt="image" src="https://github.com/user-attachments/assets/4828ec0c-efc5-45fc-a36c-d80027e7e412" />


#### 14. Read the image ('Boy.jpg').
```python
img = cv2.imread(r'C:\Users\waran\boy.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img)
plt.title('Original Image')
plt.axis('off')
plt.show()
```

<img width="260" height="209" alt="image" src="https://github.com/user-attachments/assets/a145f287-5869-4227-859d-f80614f25999" />


#### 15. Adjust the brightness of the image.
```python
matrix_ones = np.ones(img.shape, dtype='uint8') * 50
print(matrix_ones)
```

<img width="61" height="220" alt="image" src="https://github.com/user-attachments/assets/a63df6d7-3b0f-4ec5-9a44-de62e7bccb6e" />

<img width="58" height="206" alt="image" src="https://github.com/user-attachments/assets/bbd02ed8-6eff-414b-b868-3a78a4f7bd62" />



#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix_ones)
img_darker = cv2.subtract(img, matrix_ones)
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
plt.figure(figsize=(15,5))

plt.subplot(1,3,1)
plt.imshow(img)
plt.title('Original')
plt.axis('off')

plt.subplot(1,3,2)
plt.imshow(img_darker)
plt.title('Darker')
plt.axis('off')

plt.subplot(1,3,3)
plt.imshow(img_brighter)
plt.title('Brighter')
plt.axis('off')

plt.show()
```

<img width="551" height="140" alt="image" src="https://github.com/user-attachments/assets/21621c57-72ad-45b3-be6e-02bdf2ab7105" />


#### 18. Modify the image contrast.
```python
matrix1 = np.ones(img.shape, dtype='uint8') * 1.1
matrix2 = np.ones(img.shape, dtype='uint8') * 1.2

img_higher1 = cv2.multiply(np.float64(img), matrix1)
img_higher2 = cv2.multiply(np.float64(img), matrix2)
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
plt.figure(figsize=(15,5))

plt.subplot(1,3,1)
plt.imshow(img)
plt.title('Original')
plt.axis('off')

plt.subplot(1,3,2)
plt.imshow(np.uint8(img_higher1))
plt.title('Contrast 1.1')
plt.axis('off')

plt.subplot(1,3,3)
plt.imshow(np.uint8(img_higher2))
plt.title('Contrast 1.2')
plt.axis('off')

plt.show()
```

<img width="551" height="148" alt="image" src="https://github.com/user-attachments/assets/6b65b702-3dca-4f5c-8a36-01d2a5bb346d" />


#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
img_bgr = cv2.imread('boy.jpg')
B, G, R = cv2.split(img_bgr)

plt.figure(figsize=(15,5))

plt.subplot(1,3,1)
plt.imshow(B, cmap='gray')
plt.title('Blue Channel')

plt.subplot(1,3,2)
plt.imshow(G, cmap='gray')
plt.title('Green Channel')

plt.subplot(1,3,3)
plt.imshow(R, cmap='gray')
plt.title('Red Channel')

plt.show()
```

<img width="555" height="146" alt="image" src="https://github.com/user-attachments/assets/0f3a6edc-406b-4cbe-996d-f0389b04868a" />


#### 21. Merged the R, G, B , displays along with the original image
```python
merged_img = cv2.merge((B, G, R))
merged_img = cv2.cvtColor(merged_img, cv2.COLOR_BGR2RGB)

plt.figure(figsize=(10,5))

plt.subplot(1,2,1)
plt.imshow(img)
plt.title('Original Image')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(merged_img)
plt.title('Merged RGB Image')
plt.axis('off')

plt.show()
```

<img width="400" height="157" alt="image" src="https://github.com/user-attachments/assets/7726e5b7-2978-45c8-a55a-5df875deb1a2" />


#### 22. Split the image into the H, S, V components & Display the channels.
```python
hsv_img = cv2.cvtColor(img_bgr, cv2.COLOR_BGR2HSV)
H, S, V = cv2.split(hsv_img)

plt.figure(figsize=(15,5))

plt.subplot(1,3,1)
plt.imshow(H, cmap='gray')
plt.title('Hue Channel')

plt.subplot(1,3,2)
plt.imshow(S, cmap='gray')
plt.title('Saturation Channel')

plt.subplot(1,3,3)
plt.imshow(V, cmap='gray')
plt.title('Value Channel')

plt.show()
```

<img width="551" height="163" alt="image" src="https://github.com/user-attachments/assets/5fe06a05-83a1-40c6-ad0c-8cb9a47c56ce" />


#### 23. Merged the H, S, V, displays along with original image.
```python
merged_hsv = cv2.merge((H, S, V))
merged_rgb = cv2.cvtColor(merged_hsv, cv2.COLOR_HSV2RGB)

plt.figure(figsize=(10,5))

plt.subplot(1,2,1)
plt.imshow(img)
plt.title('Original Image')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(merged_rgb)
plt.title('Merged HSV Image')
plt.axis('off')

plt.show()
```

<img width="399" height="155" alt="image" src="https://github.com/user-attachments/assets/4b65af1b-d0a7-4284-85a8-ac38c66d86eb" />


## Output:
- **i)** Read and Display an Image.  
- **ii)** Adjust Image Brightness.  
- **iii)** Modify Image Contrast.  
- **iv)** Generate Third Image Using Bitwise Operations.

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
