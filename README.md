# workshop-dipt
# Program
## 1) Load the images
```
import cv2
img1=cv2.imread('Downloads/download1.jpg')
img2=cv2.imread('Downloads/download2.jpg')
cv2.imshow('Original image_1',img1)
cv2.imshow('Original image_2',img2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## 2) Divide images into four parts
```
h1, w1, _ = img1.shape

if img1.shape != img2.shape:
    img2 = cv2.resize(img2, (w1, h1))

h2, w2, _ = img2.shape
R1=img1[0:h1//2,0:w1//2]
R2=img1[h1//2:h1,0:w1//2]
R3=img1[0:h1//2,w1//2:w1]
R4=img1[h1//2:h1,w1//2:w1]

R5=img2[0:h2//2,0:w2//2]
R6=img2[h2//2:h2,0:w2//2]
R7=img2[0:h2//2,w2//2:w2]
R8=img2[h2//2:h2,w2//2:w2]

cv2.imshow('Original image_1',img1)
cv2.imshow('top_left',R1)
cv2.imshow('bottom_left',R2)
cv2.imshow('top_right',R3)
cv2.imshow('bottom_right',R4)
cv2.waitKey(0)
cv2.destroyAllWindows()

cv2.imshow('Original image_2',img2)
cv2.imshow('top_left',R5)
cv2.imshow('bottom_left',R6)
cv2.imshow('top_right',R7)
cv2.imshow('bottom_right',R8)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## 3) Swap the images
```
temp = R1.copy()
R1[:] = R8
R8[:] = temp

temp = R2.copy()
R2[:] = R7
R7[:] = temp

new_image1 = cv2.vconcat([cv2.hconcat([R1, R2]), cv2.hconcat([R3, R4])])
new_image2 = cv2.vconcat([cv2.hconcat([R5, R6]), cv2.hconcat([R7, R8])])

cv2.imshow('New Image 1', new_image1)
cv2.imshow('New Image 2', new_image2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## 4) Resizes images
```
new_image1 = cv2.resize(new_image1,(134,134))
new_image2 = cv2.resize(new_image2,(134,134))
cv2.imshow('New Image 1', new_image1)
cv2.imshow('New Image 2', new_image2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# Output
## 1) Load the images
### image1
<br>

![image](https://github.com/user-attachments/assets/32135b46-1c9c-4604-b002-63c6c04946f5)

<br>

### image2
![image](https://github.com/user-attachments/assets/f3e4b522-199b-4701-a7b8-7d8c6e0bcf2e)

<br>

## 2) Divide images into four parts
### image1
<br>

![image](https://github.com/user-attachments/assets/e12f06b5-d85d-4460-aa74-175bacd8ab8d)

![image](https://github.com/user-attachments/assets/ab97b8b5-92d6-420c-8eb9-f9bc84f7b5c5)

![image](https://github.com/user-attachments/assets/70d46f72-1f99-4cf8-86fb-8e604fef7f7d)

![Screenshot 2024-09-01 152305](https://github.com/user-attachments/assets/ed3c3c9f-6de9-45c9-8aec-2fa7698cb4c7)

<br>

### image2

<br>

![image](https://github.com/user-attachments/assets/88e44bad-c2d9-427e-92fd-2458c5fc25e4)


![image](https://github.com/user-attachments/assets/4f1b0417-bb17-44a6-a2bd-df3cdc37e970)


![image](https://github.com/user-attachments/assets/7252f69c-9b8b-4574-8b01-038c44cfd667)


![image](https://github.com/user-attachments/assets/4638972f-f8cc-4174-a35d-9fa7e9489ec7)

<br>

## 3) Swap the images

### R1 and R8
<br>

![image](https://github.com/user-attachments/assets/d70493eb-27b1-436e-913e-9cff188406c2)

![image](https://github.com/user-attachments/assets/39d23a4e-5a3c-4038-bd0e-21ec06d237f9)

<br>

### R2 and R7
<br>

![image](https://github.com/user-attachments/assets/c00ea4a8-6a28-4ac5-9e09-9591f88ded92)


![image](https://github.com/user-attachments/assets/450dbe9c-6240-485e-b5f8-d462ce32ef0b)

![image](https://github.com/user-attachments/assets/59b5aa90-6371-4dd6-bf11-e1e7793cb3d8)

<br>

## 4) Resizes images

<br>

![image](https://github.com/user-attachments/assets/185c3ace-c3fa-4273-8c82-259dbdbae35c)

![image](https://github.com/user-attachments/assets/390646ea-61a9-4d09-a107-e25f4fe454a6)


<br>
