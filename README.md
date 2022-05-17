# Edge-Detection
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the required packages.


### Step2:
Load the image to operate on.

### Step3:
Convert the image to grayscale image.

### Step4:
Use Sobel operator along x,y and xy directions.

### Step5:
Operate the image using Laplacian operator.

### Step6:
Operate the image using Canny Edge operator.

### Step7:
Show all the operated images output.

### Step8:
End the program.
 
## Program:

``` Python
# Import the packages
import cv2
import matplotlib.pyplot as plt



# Load the image, Convert to grayscale and remove noise
image=cv2.imread("puppyy.jpg")
gray=cv2.cvtColor(image,COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)




# SOBEL EDGE DETECTOR
sobelx = cv2.Sobel(img,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(img,cv2.CV_64F,0,1,ksize=5)
sobelxy =cv2.Sobel(img,cv2.CV_64F,1,1,ksize=5)
plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(img,cmap = 'gray')
plt.title('Original'), plt.xticks([]), plt.yticks([])

plt.subplot(2,2,2)
plt.imshow(sobelx,cmap= 'gray')
plt.title('sobelx')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,3)
plt.imshow(sobely,cmap= 'gray')
plt.title('sobely')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,4)
plt.imshow(sobelxy)
plt.title('sobelxy')
plt.xticks([]), plt.yticks([])
plt.show()
# cv2.waitKey(0)



# LAPLACIAN EDGE DETECTOR
laplacian = cv2.Laplacian(img,cv2.CV_64F)
plt.imshow(laplacian)
plt.title('laplacian')
plt.show()



# CANNY EDGE DETECTOR
canny_edges = cv2.Canny(img, 120, 150)
plt.imshow(canny_edges)
plt.title('canny_edges')
plt.show()




```
## Output:
### SOBEL EDGE DETECTOR

![output](orig1.PNG)
![output](sobelx.PNG)
![output](sobely.PNG)
![output](sobelxy.PNG)

### LAPLACIAN EDGE DETECTOR
![output](laplacian.PNG)


### CANNY EDGE DETECTOR
![output](cannyed.PNG)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
