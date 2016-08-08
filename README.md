# picture
import cv2
import sys
import os

# usage: python ex_001.py path/to/image.jpg
imgPath = sys.argv[1]
if not os.path.isfile(imgPath):
    print("Image file not found.")
    sys.exit()

# read in the image
img = cv2.imread(imgPath)

# display the image and wait for key press
cv2.imshow('original', img)
cv2.waitKey(0)

# convert to grayscale and display
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

cv2.imshow('grayscale', gray)
cv2.waitKey(0)

# apply a blue and display
blurred = cv2.blur(gray, (9, 9))
cv2.imshow('blurred', blurred)
cv2.waitKey(0)
