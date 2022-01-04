# ImageProcessing_PengolahanCitra
membaca gambar dari url, dan menampilkannya menggunakan openCV, perbedaan saat membaca gambar dalam format RGB dan BGR. Saluran warna input default dalam format BGR untuk openCV.
import numpy as np
import pandas as pd
import cv2 as cv 
from google.colab.patches import cv2_imshow # for image display
from skimage import io
from PIL import Image 
import matplotlib.pylab as plt

# Create a list to store the urls of the images
urls = ["https://pasca-sarjana.com/wp-content/uploads/2019/11/gedung-1.jpg",
       "https://iiif.lib.ncsu.edu/iiif/0016007/full/800,/0/default.jpg",
      "https://placekitten.com/800/571"]  
# Read and display the image
# loop over the image URLs, you could store several image urls in the list

for url in urls:
  image = io.imread(url) 
  image_2 = cv.cvtColor(image, cv.COLOR_BGR2RGB)
  final_frame = cv.hconcat((image, image_2))
  cv2_imshow(final_frame)
  print('\n')
