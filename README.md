# Experiment 1: Image Handling and Pixel Transformations Using OpenCV

## Name: DHIVYASHREE R  
## Register Number: 212225040077  
## Experiment: Image Handling and Pixel Transformations Using OpenCV

---

## AIM

To perform image handling and pixel transformations using Python and OpenCV, including reading and displaying images, drawing shapes, adding text, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving the modified image.

## SOFTWARE REQUIRED

- Python
- OpenCV
- Matplotlib
- Jupyter Notebook
- Anaconda (optional)

## INSTALLATION

Install the required libraries using the following command:

```bash
pip install opencv-contrib-python-headless matplotlib
```

## ALGORITHM

### Step 1: Read and Display an Image

1. Import OpenCV and Matplotlib libraries.
2. Read an image from the local directory using `cv2.imread()`.
3. Convert the image from BGR to RGB.
4. Display the original image using Matplotlib.

### Step 2: Draw Shapes and Add Text

1. Draw a line from the top-left to the bottom-right of the image.
2. Draw a circle at the center of the image.
3. Draw a rectangle around the image.
4. Add the text "OpenCV Drawing" at the top-left corner.

### Step 3: Color Space Conversion

1. Convert the RGB image to HSV and display it.
2. Convert the RGB image to grayscale and display it.
3. Convert the RGB image to YCrCb and display it.
4. Convert the HSV image back to RGB and display it.

### Step 4: Pixel Manipulation

1. Access and print the pixel value at coordinates `(100, 100)`.
2. Change the pixel at coordinates `(200, 200)` to white.
3. Modify a 300 × 300 region of the image to white.
4. Display the modified image.

### Step 5: Image Resizing

1. Read the original image.
2. Resize the image to half its original width and height.
3. Display the resized image.

### Step 6: Image Cropping

1. Read the original image.
2. Extract a 300 × 300 region of interest starting at `(50, 50)`.
3. Display the cropped image.

### Step 7: Image Flipping

1. Flip the original image horizontally.
2. Flip the original image vertically.
3. Display both flipped images.

### Step 8: Save the Final Modified Image

1. Save the modified image in the local directory using `cv2.imwrite()`.
2. Verify that the image has been saved successfully.

### program
### Step 1: Read and Display an Image
import cv2
import matplotlib.pyplot as plt

# Read the image using OpenCV
img = cv2.imread('me.jpeg', cv2.IMREAD_COLOR)

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

### Step 2: Draw Shapes and Add Text

#### 2.1 Draw a Line

python
# Load the image
image = cv2.imread('me.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape

# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)

# Display the image
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
#### 2.2 Draw a Circle

python
# Load the image
image = cv2.imread('me.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)

# Display the image
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

#### 2.3 Draw a Rectangle

python
# Load the image
image = cv2.imread('me.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape

# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

# Display the image
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
#### 2.4 Add Text to the Image

python
# Load the image
image = cv2.imread('me.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(img_rgb, "DHIVYASHREE", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)


# Display the image
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()


### Step 3: Color Space Conversion

python
# Load the image
image = cv2.imread('varshan.jpeg') 

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")

# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
### Step 4: Pixel Manipulation

python
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()


### Step 5: Image Resizing

python
image = cv2.imread('me.jpeg') 
image.shape

# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

resized_image_rgb.shape

# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

### Step 6: Image Cropping

python
# Load the image
image = cv2.imread('me.jpeg')

image.shape

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

### Step 7: Image Flipping

python
# Load the image
image = cv2.imread('me.jpeg')

# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)

# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")

## OUTPUT

# The following outputs are obtained:

# 1. Original image displayed using OpenCV and Matplotlib.

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/1ece9bdb-0b05-4f92-a770-29f5f7cd9c4e" />




# 2. Image with a line drawn from the top-left to the bottom-right.

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/eb9846ec-0668-4e0b-82d2-4e8bba23a573" />


# 3. Image with a circle at the center.

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/c3d3557a-e747-43fb-82b0-c62f4441b488" />



# 4. Image with a rectangle around its boundary.

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/aead425d-6def-4824-923c-d6b116c6f853" />


# 5. Image with the text "OpenCV Drawing".

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/c4cc0bc4-012c-4ff3-838d-671f5ab1df35" />



# 6. HSV, grayscale, and YCrCb color space conversions.


<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/52f88ac8-a064-4e8d-9c84-038828dc8ed5" />


<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/9b318e22-7dfd-4467-8d24-0258035a47cf" />

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/ec7945a5-2157-4ed7-af18-8530456b6d13" />



# 7. Image converted from HSV back to RGB.

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/a04d098d-7d5c-4e73-959b-7c5f36692317" />


# 8. Pixel value displayed and a white region added to the image.

<img width="302" height="410" alt="image" src="https://github.com/user-attachments/assets/c3c2e39c-07f7-49b4-a300-101504b24b1c" />



# 9. Image resized to half its original dimensions.

<img width="493" height="410" alt="image" src="https://github.com/user-attachments/assets/6428251b-4303-4a01-8fc7-a1ef7ad50f04" />

# 10. Cropped region of interest displayed.

<img width="389" height="410" alt="image" src="https://github.com/user-attachments/assets/f5569762-8a9c-43c7-98a9-b64e3f84a837" />


# 11. Horizontally flipped image displayed.

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/18f70a00-9e8c-4736-adec-2cad1bc5f58e" />


# 12. Vertically flipped image displayed.
<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/68121264-4e9e-4b7e-96c9-e6e9917ecc4b" />


## RESULT

Thus, image handling and pixel transformations were performed using Python, OpenCV, and Matplotlib. The experiment demonstrated image reading, shape drawing, text insertion, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving.
 arrange properly for github without changing content
