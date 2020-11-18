# Task 1: Detect Building Blocks
This task consist in detecting a set of closed shapes (building blocks) in the map image.

Building blocks are coarser map objects which can regroup several elements.
Detecting these objects is a critical step in the digitization of historical maps because it provides essential components of a city.
Each building block is symbolized by a closed which can enclose other objects and lines.
Building blocks are surrounded by streets, rivers fortification wall or others, and are never directly connected.
Building blocks can sometimes be reduced to a single spacial building, symbolized by diagonal hatched areas.


Given the image of a complete map sheet and a mask of the map area, you need to detect each building block, as illustrated below on a excerpt of the input.
<center>
![Excerpt of the input for task 1](../img/task1-input-detail.jpg)
*Excerpt of the input for task 1*
</center>

<center>
![Excerpt of the expected output for task 1](../img/task1-output_illustration-detail.jpg)
*Excerpt of the expected output for task 1*
</center>

We identified the following challenges:

1. Building blocks can have very variable sizes.
2. They can be reduced to a single building (diagonal hatched area).
3. Their contour can be damaged (ie non-closed).
4. Several other layers of information can be overlaid on building block outlines (text, railways, underground lines, graticule lines among others).
5. There may be decompositions inside a building block, increasing the number of edges to filter.
6. Building blocks may be large empty areas only surrounded by a contour. The lack of texture information and the variable sizes may be challenging to multiscale texture methods like convolutional neural networks.
7. Producing closed contours requires to embed strong guarantees in the method.


## Input
The inputs form a set of JPEG RGB images like the one illustrated below.
There are complete map sheet images cropped to the relevant area for which the non-relevant area is replaced by black pixels, as illustrated below.
Those images can be large (8000x8000 pixels).

<center>
![Sample input for task 1](../img/task1-input-large.jpg)
*Sample input for task 1: non relevant pixels are replaced by black pixels.*
</center>

To help participants identify the non-relevant pixels, we also provide a mask image for which non-relevant pixels have value `0` and relevant pixels have value `255`, as illustrated below. Theses masks are the expected output for task 2 (cropped to the relevant part).

<center>
![Extra input mask for task 1](../img/task2-output-large.jpg)
*Extra input mask for task 1 (exact same format as the output for task 2): indicates the masked content.*
</center>

## Ground truth and Expected outputs
Expected output for this task is a binary mask of the building blocks.
It must be stored in PNG (lossless) format with an 8-bit single channel.
Background must be indicated with pixel value 0, and building block areas with pixel value 255.
We will threshold the image to discard any other value.

The resulting image should look like the one below, which is the expected output for the sample input previously shown.

<center>
![Sample output for task 1](../img/task1-output-large.jpg)
*Sample output for task 1*
</center>

Results need to be output in a PNG file with the exact same format and naming conventions as the ground truth, except for the `GT` part of the filename which should be changed into `PRED`:
if the input image is named `train/301-INPUT.jpg`, then the output file must be named `train/301-OUTPUT-PRED.png`.

## Dataset

Content for task 1 is located in the folder named `1-detbblocks` in the dataset archive.

### File naming conventions
Train, validation and test folder (if applicable) contain the same kind of files:

- `${SUBSET}/${NNN}-INPUT.jpg`:  
  JPEG RGB image containing the input image to process.
  This image was cropped to map content and irrelevant content (masked out by the mask file described below) are set to black (RGB=`(0,0,0)`).
  Those images can be large (10000x10000 pixels).  
  > *example:*  
  > `1-detbblocks/train/101-INPUT.jpg`
- `${SUBSET}/${NNN}-INPUT-MASK.png`:  
  PNG GREY image containing a mask of the map area (same size as input).
  While the image was cropped to the meaningful area, some elements need to be discarded (map legend for instance).
  Map area is indicated by pixels of value `255`; only predictions within this area is to be kept.  
  > *example:*  
  > `1-detbblocks/train/101-INPUT-MASK.png`
- `${SUBSET}/${NNN}-OUTPUT-GT.png`:  
  PNG GREY image containing a mask of expected building blocks (same size as input).
  Building blocks are indicated by pixels of value `255`; all other pixels (background and irrelevant) are set to `0`.
  > *example:*  
  > `1-detbblocks/train/101-OUTPUT-GT.png`


### Number of elements per set
- train: 1 image
- validation: 1 image
- test: 3 images


## Evaluation
**Evaluation tools and illustrative notebooks provide participants with more details than the summary below.**
*Please [subscribe to updates](../contact.md#subscribe-to-updates) to be notified when they are available.*

For each map sheet, we will extract the connected components from the predicted label mask.
Based on this mask, we will compute the intersection over union (IoU) between each ground truth component and each predicted one, and retain only the matches with a value of at least $`0.5`$.
When the IoU is strictly superior to $`0.5`$ we have 1-to-1 matches between ground truth components and predicted ones, and this enables the computation of prediction, recall and $`F_1`$ scores.

We will compute the $`F_1`$ values for each possible IoU threshold in $`]0.5, 1]`$ and compute the area under the resulting curve.
Such score will not only be free of any threshold, it will also be insensitive to shape area; thus weighting large and small shapes equally and provided an accurate measure of the number of objects properly detected.

Finally, we will compute the average of the measures for all individual map images to produce a global indicator.

The resulting measure is a float value between 0 and $`0.5`$.
A high value is better.

