# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.


##### Program:
### Developed By: RIYA P L
### Register Number: 212223240141

### i)Read and Display an Image
```
import cv2
image=cv2.imread('naturek.jpg',1)
image = cv2.resize(image, (400, 300))
cv2.imshow('NATUREK',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## OUTPUT:
![Screenshot 2024-09-02 134836](https://github.com/user-attachments/assets/8d9bafa3-499e-4f50-b694-3e2cd3a74cca)

### ii)Write the image
```
image=cv2.imread('filename.jpg',0)
cv2.imwrite('copy2.jpeg',image)
```
## OUTPUT:
![Screenshot 2024-09-02 141028](https://github.com/user-attachments/assets/c6f60d2e-114d-4343-95fe-a9e5d85352ff)

### iii)Shape of the image
```
import cv2
image=cv2.imread('filename.jpg',1)
print(image.shape)
```
## OUTPUT:
![Screenshot 2024-09-02 141044](https://github.com/user-attachments/assets/48ef8b1f-a470-4239-b77f-a617e0993b49)

### iv)Access and Manipulate Image Pixels
```
import random
import cv2
image=cv2.imread('filename.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('Rome part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT:
![Screenshot 2024-09-02 134942](https://github.com/user-attachments/assets/bc98c409-6453-4b54-b2fd-b13f9afa34fa)

### v)Image Resizing cut and paste
```
import cv2
image=cv2.imread('filename.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[130:200,110:190]
image[110:180,120:200] = tag
cv2.imshow('cut and paste',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT:
![Screenshot 2024-09-02 135037](https://github.com/user-attachments/assets/19a05114-ba73-428c-b261-b09068021900)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('filename.jpg',1)
img = cv2.resize(img,(300,300))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT:
![Screenshot 2024-09-02 135144](https://github.com/user-attachments/assets/0456450d-4154-482f-b28d-86b54b8019ba)
![Screenshot 2024-09-02 135157](https://github.com/user-attachments/assets/6739101e-dc7e-4f1c-9c21-ffdfced9e4ff)
![Screenshot 2024-09-02 135211](https://github.com/user-attachments/assets/3bbbd93e-059a-48a6-ac4f-2920a6d335d4)
![Screenshot 2024-09-02 135225](https://github.com/user-attachments/assets/acbd6d01-ea96-4ac7-99e4-00e811d203e8)
![Screenshot 2024-09-02 135237](https://github.com/user-attachments/assets/9992a10b-694c-4ec9-a7e2-90c426b35fb2)

### vii)HSV to RGB and BGR
```
import cv2
img = cv2.imread('filename.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT:
![Screenshot 2024-09-02 135334](https://github.com/user-attachments/assets/67b710e9-82ed-4b95-ad18-a3f9c015935a)
![Screenshot 2024-09-02 135347](https://github.com/user-attachments/assets/5a03f5a7-392e-4d10-8fc4-f1dc4a888520)
![Screenshot 2024-09-02 135430](https://github.com/user-attachments/assets/3802f066-95d2-4dc7-b665-6bd0fe506405)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('filename.jpg')
img = cv2.resize(img,(300,300))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT:
![Screenshot 2024-09-02 135512](https://github.com/user-attachments/assets/6fa5e6df-c0a4-4b73-8965-d11b7c17b928)
![Screenshot 2024-09-02 135521](https://github.com/user-attachments/assets/a105e491-5b5a-4d24-b5c9-9b1cfa8a3848)
![Screenshot 2024-09-02 135536](https://github.com/user-attachments/assets/5275e387-9efa-48c1-9749-094150cc8195)

### xi)Split and merge RGB Image
```
import cv2
img = cv2.imread('filename.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT:
![Screenshot 2024-09-02 135615](https://github.com/user-attachments/assets/1280f8cf-84b3-4a8a-8298-7e5e362d9424)
![Screenshot 2024-09-02 135629](https://github.com/user-attachments/assets/b554449a-6405-4049-b6e2-b1934c2a4e3a)
![Screenshot 2024-09-02 135639](https://github.com/user-attachments/assets/5bd49c03-d412-4de4-8481-4c8022f1d20b)
![Screenshot 2024-09-02 135651](https://github.com/user-attachments/assets/45e63e17-4dc9-4a58-a262-b62ac422b083)

### X)Split and merge HSV Image
```
img = cv2.imread("filename.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT:
![Screenshot 2024-09-02 140321](https://github.com/user-attachments/assets/35882a62-ed43-4256-9abb-a4fa4089a416)
![Screenshot 2024-09-02 140347](https://github.com/user-attachments/assets/162e75d1-fe9d-4fec-a10b-e25cb950cc42)
![Screenshot 2024-09-02 140400](https://github.com/user-attachments/assets/f5bbdfce-8fc4-49c9-ba9d-d236634880b1)
![Screenshot 2024-09-02 140548](https://github.com/user-attachments/assets/93acb783-80d7-486a-9811-63fc3f374dea)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







