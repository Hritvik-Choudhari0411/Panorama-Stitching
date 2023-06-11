# Panorama-Stitching
Here we perform image stitching using sequence of images.

# Installation
Install the below libraries to run the code without issues.
- opencv-contrib-python
- matplotlib
- numpy
- random

Install all libraries using the command below and replace `<name>` with above options.
```
pip3 install <name>
```
# Steps to perform image stitching
1. Finding features between consecutive pair of images using SIFT feature matcher. We get multiple features and their corresponding matches. We use Brute force matcher to get matches.
2. Apply RANSAC algorithm to remove the outliers from the features list obtained in order to make the stitching process more robust and accurate. 
3. Now we extract the pixel coordinates of each keypoint from the list and use them to calculate the homography matrix. 
4. We then use warpPerspective function that takes the train image, homography matrix and image dimensions to calculate the warp of train image w.r.t query image.
5. Now we insert query image in warp image obtained in the region defined by its
shape to get the stitching between the two and finally crop the image.
# Code run
Make sure that below folders are in the same directory as the code file.
- image_1.jpg
- image_2.jpg
- image_3.jpg
- image_4.jpg

To run the code file, run command:
```
python3 Q2.py
```

# Results
- Image sequences
<p align="center">
<img src="https://github.com/Hritvik-Choudhari0411/Panorama-Stitching/blob/main/images/image_1.jpg" width="200" height="200"/>
<img src="https://github.com/Hritvik-Choudhari0411/Panorama-Stitching/blob/main/images/image_2.jpg" width="200" height="200"/>
<img src="https://github.com/Hritvik-Choudhari0411/Panorama-Stitching/blob/main/images/image_3.jpg" width="200" height="200"/>
<img src="https://github.com/Hritvik-Choudhari0411/Panorama-Stitching/blob/main/images/image_4.jpg" width="200" height="200"/>
</p>
- Panorama stitched image
- <p align="center">
<img src="https://github.com/Hritvik-Choudhari0411/Panorama-Stitching/blob/main/Panorama%20stitch.png" width="700" height="400"/>
</p>
