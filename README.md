# SemiSeg
Code for Semi-Automated Segmentation of Microscopic Video Data.  Created for Widefield Fluorescent Calcium Imaging data formatted as tiff stacks in Mice.  Nothing too novel used, as many techniques are used in commercial packages, but I needed something I could get under the hood with and alter things as necessary. I often use this code to generate my "ground-truth" values for segmentation projects, as I get dynamic feedback through the code and have my own personal certainty in the results that are outputted as my ground-truth. Uses built-in matlab functions to navigate the images and select regions of interest (ROIs) thresholded on various processed versions of the images, as described below.

1.  Raw Image - Threshold is determined from Max-Min projection across the video stack. This is the standard image that is shown.
2.  Cross Correlation Image - Threshold is determined from pixel-wise cross correlation across time for zoomed-in image selection, to speed up processing and allow this computation on large/high-resolution video files.
3.  Principal Component Analysis - Threshold is determined independenly for the first 3 principle components of the time traces across the zoomed-in image selection. ROIs are created for all values above a percentile threshold for any of those components and merged into one ROI.
