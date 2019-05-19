# Face Detection using Convolutional Neural Networks
Grad project for Machine Learning Course (Fall 18)

Tools used - Keras Lib, Tensorflow, Python

Utilized Labelled faces provided by University of Massachusetts as positives and used INRIA and Caltech 101 dataset for the negatives.     

Partitioned training data into training and validation sets with 75% for training and 25% for validation. We also augment the number of images we have using “ImageDataGenerator” to boost the performance over our validation set.                                               

Detection:

To detect faces of different scales in an image, we need to have an image pyramid.  An “image pyramid” is a multi-scale representation of an image. At the bottom of the pyramid we have the original image at its original size (in terms of width and height). And at each subsequent layer, the image is resized (subsampled) and optionally smoothed (usually via Gaussian blurring). The image is progressively subsampled until some stopping criterion is met, which is normally a minimum size has been reached and no further subsampling needs to take place.                                                                                                                               

 Sliding windows play an integral role in object classification, as they allow us to localize exactly where in an image our object of interest resides. A sliding window is rectangular region of fixed width and height that slides across an image. For each of these windows, we take the window region and apply our CNN model to determine if the window has an object that interests us — in this case, a face.        
 Utilizing both a sliding window and an image pyramid we can detect faces in images at various scales and locations. For each window in each image in the pyramid, we apply our face/not-face model to detect faces if they return a confidence greater than 99%.                 

Achieved accuracy of 92% for the various test images.
