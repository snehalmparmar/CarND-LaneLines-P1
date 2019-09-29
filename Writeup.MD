# **Finding Lane Lines** 

The purpose of this project is to develope a software to create a pipeline to find lane lines on the road using Python and OpenCV library.


![solid-yellow-left](Test_OutputVideoDir/solidYellowLeft.gif) | ![solid-white-right-line](Test_OutputVideoDir/solidWhiteRight.gif) | ![challenge](Test_OutputVideoDir/challenge.gif)
--- | --- | ---

---

## Description of the Pipeline

The pipeline consists of the following steps:

- **Convert images into grayscale**

<img src="https://github.com/snehalmparmar/CarND-LaneLines-P1/blob/0bf7add102f3998369d69182324a3918dd1b5c34/Test_GrayImageDir/solidYellowCurve.jpg" width="480" alt="Converted into grayscale" />

- **Apply a Gaussian blur algorith**

<img src="https://github.com/snehalmparmar/CarND-LaneLines-P1/blob/0bf7add102f3998369d69182324a3918dd1b5c34/Test_BlurImageDir/solidYellowCurve.jpg" width="480" alt="Gaussian blur" />

- **Apply Canny edge transform algorithm**

<img src="https://github.com/snehalmparmar/CarND-LaneLines-P1/blob/0bf7add102f3998369d69182324a3918dd1b5c34/Test_CanyImageDir/solidYellowCurve.jpg" width="480" alt="Canny edge" />

- **Mask part of the images outside of the region of interest for lines finding**

<img src="https://github.com/snehalmparmar/CarND-LaneLines-P1/blob/0bf7add102f3998369d69182324a3918dd1b5c34/Test_MaskedImageDir/solidYellowCurve.jpg" width="480" alt="Region of interest" />

- **Apply Hough transform algorithm to find the lines**

- **Separate left lines from right ones and filter it by slope boundaries**

- **Fit a single straight line and smooth the result by taking into account the ten previous images**

- **Draw the lines on top of the original image**

<img src="https://github.com/snehalmparmar/CarND-LaneLines-P1/blob/0bf7add102f3998369d69182324a3918dd1b5c34/Test_LineImagesDir/solidYellowCurve.jpg" width="480" alt="Region of interest" />

The output for each step is saved in the following directories:

- [Test_GrayImageDir](https://github.com/snehalmparmar/CarND-LaneLines-P1/tree/0bf7add102f3998369d69182324a3918dd1b5c34/Test_GrayImageDir)
- [Test_BlurImageDir](https://github.com/snehalmparmar/CarND-LaneLines-P1/tree/0bf7add102f3998369d69182324a3918dd1b5c34/Test_BlurImageDir)
- [Test_CanyImageDir](https://github.com/snehalmparmar/CarND-LaneLines-P1/tree/0bf7add102f3998369d69182324a3918dd1b5c34/Test_CanyImageDir)
- [Test_MaskedImageDir](https://github.com/snehalmparmar/CarND-LaneLines-P1/tree/0bf7add102f3998369d69182324a3918dd1b5c34/Test_MaskedImageDir)
- [Test_LineImagesDir](https://github.com/snehalmparmar/CarND-LaneLines-P1/tree/0bf7add102f3998369d69182324a3918dd1b5c34/Test_LineImagesDir)

Refer following directory for the videos: [Test_OutputVideoDir](https://github.com/snehalmparmar/CarND-LaneLines-P1/tree/0bf7add102f3998369d69182324a3918dd1b5c34/Test_OutputVideoDir)

## Potential shortcomings

(1) If this pipeline is applied to a low contrast video such as the challenge video which is part of this project, it will find lanes and draw lines but they won’t be completely overlaping with the original lanes. To overcome this, the first step of the pipeline can be a color selection with white and yellow in the picture/videos and then apply rest of the steps. When I tried with color selection as first step it worked perfectly on the challenge video but it disturbed little bit lane overlapping on other two high contrast videos (solidWhiteRight, and solidYellowLeft). 

(2) On videos, the lanes are not steady but it shakes little bit. I wish it could be smooth. 
 
## Possible improvement

1) As mentioned above in shortcoming#1, the pipeline could be improved to apply color selections on both high contrast and low contrast videos to give the same results. I have applied color selection only on the challenge video which is a low contrast video. I couldn’t apply it on other videos because that disturbed lanes. 

2) Pipeline could be tuned to overcome the issue of lane shaking. 
