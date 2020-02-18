import sys,os
import PIL.Image as image
import numpy as np
import matplotlib.pyplot as plt
from scipy import signal

img= image.open("C:\\Users\\user\\Desktop\\TEST2.png")
img2 = img.resize((128,128))

print(img2.size)

pixel = np.array(img2)
print(np.shape(pixel))
pix = pixel[:,:,0]
print("PIX : ", np.shape(pix))

for a in range(128):
    for b in range(0,128):
        if pix[a,b] < 30: pix[a,b] = 0
        else: pix[a,b] = 1


plt.imshow(pix)
plt.show()

we_1 = np. array([[0,0,0],[1,1,1],[0,0,0],],dtype='float')
we_2 = np. array([[0,1,0],[0,1,0],[0,1,0],],dtype='float')
we_3 = np. array([[1,0,0],[0,1,0],[0,0,1],],dtype='float')
we_4 = np. array([[-1,0,1],[-2,0,2],[-1,0,1],],dtype='float')

re_1 = signal.convolve2d(pix,we_1,'valid')
re_2 = signal.convolve2d(pix,we_2,'valid')
re_3 = signal.convolve2d(pix,we_3,'valid')
re_4 = signal.convolve2d(pix,we_4,'valid')


ncols = 1
nrows = 4
fig, axeslist = plt.subplots(ncols=ncols, nrows=nrows)
axeslist.ravel()[0].imshow(re_1)
axeslist.ravel()[1].imshow(re_2)
axeslist.ravel()[2].imshow(re_3)
axeslist.ravel()[3].imshow(re_4)
plt.show()



iter = 5


testconv = re_1
for i in range(iter):
    temp = signal.convolve2d(testconv,we_1,'valid')
    testconv = temp
        
re_1 = testconv


testconv = re_2
for i in range(iter):
    temp = signal.convolve2d(testconv,we_2,'valid')
    testconv = temp
        
re_2 = testconv

testconv = re_3
for i in range(iter):
    temp = signal.convolve2d(testconv,we_3,'valid')
    testconv = temp
        
re_3 = testconv

testconv = re_4
for i in range(iter):
    temp = signal.convolve2d(testconv,we_4,'valid')
    testconv = temp
        
re_4 = testconv


fig, axeslist = plt.subplots(ncols=ncols, nrows=nrows)
axeslist.ravel()[0].imshow(re_1)
axeslist.ravel()[1].imshow(re_2)
axeslist.ravel()[2].imshow(re_3)
axeslist.ravel()[3].imshow(re_4)
plt.show()

print('END')

