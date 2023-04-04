# RANSAC-based-Image-Stitching
A mosaic/panorama application using Python. A panorama is a wide-angle image constructed by compositing together a number of images with overlapping fields-of-view in a photography plausible way.

Write code to construc a mosaic based on affine transformation. The images for the project is provided in the repo. 

An affine transformation is equivalent to the composed effects of translation, rotation, isotropic scaling and shear.
Formally, an affine transformation of an image coordinate, x1, is given by the matrix equation x2 = Tx1 + c. The
unknowns are given by the elements in the 2 × 2 matrix T and the 2 × 1 vector c. These image pairs have been created
synthetically to ensure that an affine transformation will be suitable.

The algorithm for the process can be found below:

1. Preprocessing
2. Detect keypoints and extract descriptors using SIFT - please check this link for more details: https://docs.opencv.org/4.x/da/df5/tutorial_py_sift_intro.html
3. Match features - Compute the distances between every SIFT descriptor
4. Prune features - Select the number of cloest matches - I wanted to deal with 200 closest distances, so 200 matches
5. Robust transformation estimation
6. Compute optimal transformation
7. Create panorama

This project can be done with both NumPy array or Kornia/Torch. I used NumPy array.
