# COLOR_CONVERSIONS_OF-IMAGE
## Aim:
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




### Program:

Developed By: G.TEJASWINI

Register Number: 212222230157


## Output:

### i) Read and display the image:
```python
    import cv2
    image=cv2.imread('flower.png',1)
    image=cv2.resize(image,(200,200))
    cv2.imshow('Tejaswini',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
<img width="272" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/0b22dbdf-b8e1-4d72-9280-7f0542b08cce">

<img width="151" alt="Screenshot 2024-02-22 200336" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/18098155-5f32-4bc5-a820-7a25682da9d8">


### ii)Write the image:
```python
    import cv2
    image=cv2.imread('flower.png',0)
    cv2.imwrite('demos.png',image)
```
<img width="272" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/9aa0bd7d-2c98-43b4-8746-9ce9b33108e1">




### iii)Shape of the Image:
```python
    import cv2
    image=cv2.imread('flower.png',1)
    print(image.shape)
```
<img width="270" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/e544a5eb-61dc-4230-94cb-e43805373f65">

### iv)Access rows and columns:
```python
import random
import cv2
image=cv2.imread('flower.png',1)
image=cv2.resize(image,(500,500))
for i in range (250,500):
 for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                     random.randint(0,255),
                     random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<img width="330" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/7c491523-edc3-42d2-9c31-5fba4c233f36">

<img width="375" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/9285626c-ef9e-4052-a89b-934a87b4ed18">



### v)Cut and paste portion of image
```python
  import cv2
  image=cv2.imread('flower.png',1)
  image=cv2.resize(image,(300,300))
  tag =image[150:200,110:160]
  image[110:160,150:200] = tag
  cv2.imshow('image1',image)
  cv2.waitKey(0)
  cv2.destroyAllWindows()
```

<img width="268" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/6b4ed340-3b67-4c06-8646-6d4fe8c739b4">

<img width="225" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/9f90a80f-e23c-4a06-902c-487cecce279e">

### vi) BGR and RGB to HSV and GRAY

```python
import cv2
img = cv2.imread('flower.png',1)
img = cv2.resize(img,(200,200))
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

<img width="332" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/24da04ed-d320-42bd-a71a-c139e5272fc1">


<img width="749" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/2522fa61-5377-42a3-8cce-195896b8a372">


### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('flower.png')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

<img width="303" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/698445b7-c8a3-401a-8db5-d12a0dd34440">


<img width="449" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/6a73f65b-cc3e-475b-8cd2-f3456277e909">

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('flower.png')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

<img width="362" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/9b7e9d4c-542e-47dd-b94f-a21cb6ae09ec">


<img width="447" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/81144f82-ac60-42a8-b5b2-5254a5d44956">

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('flower.png',1)
img = cv2.resize(img,(200,200))

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

<img width="281" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/e65e0c8a-c178-46a0-8ee5-2331f5ff58d1">


<img width="605" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/d92f4c24-96a8-49a8-9eef-fdfaa0820e8c">

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("flower.png",1)
img = cv2.resize(img,(200,200))
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

<img width="313" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/04faac01-a956-4e42-a462-a70b96f656fc">


<img width="599" alt="image" src="https://github.com/TejaswiniGugananthan/COLOR_CONVERSIONS_OF-IMAGE/assets/121222763/7329c523-5639-4df5-9624-e8f2763a238f">


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







