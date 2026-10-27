# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

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
 ## Name:SHRAVANI M
 ## Register Number:212224230263

  ## Ex. No. 01
```python
import cv2
import matplotlib.pyplot as plt
```
```python
# Read the image using OpenCV
img = cv2.imread('photo.jpeg', cv2.IMREAD_COLOR)
```
```python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

```python
# Display the image using matplotlib imshow().
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
## OUTPUT :

<img width="356" height="417" alt="Original Image" src="./images/01_original.png" />


```python
# Load the image
image = cv2.imread('photo.jpeg') 
```
```python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```

<img width="244" height="43" alt="Image Shape" src="./images/02_shape.png" />

```python
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
```
```python
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

## OUTPUT :

<img width="397" height="421" alt="Image with Line" src="./images/03_line.png" />


```python
# Load the image
image = cv2.imread('photo.jpeg')

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape

```
## OUTPUT :

<img width="244" height="43" alt="Image Shape" src="./images/04_shape.png" />


```python
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
```

```python
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

## OUTPUT :

<img width="387" height="413" alt="Image with Circle" src="./images/05_circle.png" />


```python
# Load the image
image = cv2.imread('photo.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
```

<img width="233" height="42" alt="Image Shape" src="./images/06_shape.png" />

```python
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
```
```python
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

## OUTPUT :

<img width="353" height="417" alt="Image with Rectangle" src="./images/07_rectangle.png" />


```python
# Load the image
image = cv2.imread('photo.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
```python
# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
```
```python
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

## OUTPUT :

<img width="392" height="412" alt="Image with Text" src="./images/08_text.png" />


```python
# Load the image
image = cv2.imread('photo.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
```python
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
## OUTPUT : 

<img width="355" height="412" alt="Original RGB Image" src="./images/09_orig_rgb.png" />

```python
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

# OUTPUT :

<img width="322" height="432" alt="HSV Image" src="./images/10_hsv.png" />


```python
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```
```python
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

## OUTPUT :

<img width="377" height="425" alt="Grayscale Image" src="./images/11_gray.png" />


```python
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```
```python
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

## OUTPUT :

<img width="322" height="417" alt="YCrCb Image" src="./images/12_ycrcb.png" />


```python
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

## OUTPUT :

<img width="357" height="413" alt="HSV to RGB Image" src="./images/13_hsv_to_rgb.png" />


```python
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
```python
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

## OUTPUT :

<img width="397" height="422" alt="Image with 300x300 White Block" src="./images/14_white_block.png" />


```python
# Load the image
image = cv2.imread('photo.jpeg')
image.shape
```
<img width="183" height="44" alt="Image Shape" src="./images/15_shape1.png" />

```python
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
```

<img width="199" height="44" alt="Resized Shape" src="./images/15_shape2.png" />

```python
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

## OUTPUT :

<img width="558" height="422" alt="Resized Image" src="./images/15_resized.png" />


```python
# Load the image
image = cv2.imread('photo.jpeg')
image.shape
```
<img width="204" height="48" alt="Image Shape" src="./images/16_shape.png" />

```python
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```
```python
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
## OUTPUT :

<img width="432" height="415" alt="Cropped ROI" src="./images/16_roi.png" />


```python
# Load the image
image = cv2.imread('photo.jpeg')

# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```
```python
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```
## OUTPUT :

<img width="382" height="410" alt="Flipped Horizontally" src="./images/17_flip_h.png" />


```python
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)

# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
```python
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
## OUTPUT :

<img width="351" height="376" alt="Flipped Vertically" src="./images/18_flip_v.png" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.