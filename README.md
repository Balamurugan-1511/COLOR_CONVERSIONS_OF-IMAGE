# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By:Bala murugan P
### Register Number: 212222230017


## Output:

### i) Read and display the image
```
import cv2
   image=cv2.imread('bm.jpg',1)
   image=cv2.resize(image,(400,300))
   cv2.imshow('Bala',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
![exp 1 pic 1 DIPT](https://github.com/user-attachments/assets/21de291b-edc6-44e8-ae45-f5a3666d3b3b)


### ii)Write the image

```
   image=cv2.imread('bm.jpg',0)
   cv2.imwrite('d.jpg',image)
```
![image](https://github.com/user-attachments/assets/0ab3e141-8fbc-49bb-841f-ad2c0b66c757)


### iii)Shape of the Image
```
    image=cv2.imread('passport photo.jpg',1)
    print(image.shape)
```
![image](https://github.com/user-attachments/assets/4fe71fc1-d899-4f2c-bd0f-4fdca1e25388)


### iv)Access rows and columns
```
    import cv2
    import random
    image=cv2.imread('bm.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![exp 1 pic 2 DIPT](https://github.com/user-attachments/assets/69954479-12c9-4249-98bd-52f3aea2bdc8)

### v)Cut and paste portion of image
```
   image=cv2.imread('bm.jpg',1)
   image=cv2.resize(image,(400,400))
   tag =image[130:200,110:190]
   image[110:180,120:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
![exp 1 pic 3 DIPT](https://github.com/user-attachments/assets/a36574c4-d419-4b34-b92c-3c6c1c51111f)



### vi) BGR and RGB to HSV and GRAY
```
img = cv2.imread('bm.jpg',1)
img = cv2.resize(img,(300,200))
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

![exp 1 pic 4 DIPT](https://github.com/user-attachments/assets/f7a5537c-f778-44dc-b695-ba816f360ca8)

### vii) HSV to RGB and BGR
```
img = cv2.imread('bm.jpg')
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
![exp 1 pic 5 DIPT](https://github.com/user-attachments/assets/e143ac37-e5de-4b25-8579-660795de751d)

### viii) RGB and BGR to YCrCb
```
img = cv2.imread('bm.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![exp 1 pic 6 DIPT](https://github.com/user-attachments/assets/ea50f4a3-d2c4-4f43-8b58-44f03d1a6f67)

### ix) Split and merge RGB Image
```
img = cv2.imread('bm.jpg',1)
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
![exp 1 pic 7 DIPT](https://github.com/user-attachments/assets/7991d643-1cec-4309-869e-52772868cc8b)

### x) Split and merge HSV Image
```
img = cv2.imread("passport photo.jpg",1)
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
![exp 1 pic 8 DIPT](https://github.com/user-attachments/assets/7e4311de-e74a-47e1-995c-1b7b8a495fbc)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







