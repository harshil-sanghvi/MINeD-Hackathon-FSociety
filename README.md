
# Project Title

Background removal from diamond images using image processing and ML techniques





## Project Definition

Image segmentation has helped to solve a variety of difficult problems. One such problem is separating the diamond from the image. We have over 2.3 million images in our dataset that contain diamonds at various angles. The shiny reflecting cuts of the diamond, as well as the shadow beneath it, make this a difficult but fascinating problem to solve. Dataset : - In the dataset there will be 14 folders each named with the SHAPE-label of diamond. - There are a total 9135 uniquely numbered diamonds each having 256 images captured at different angles. - Datasets folder link: https://drive.google.com/drive/folders/1FPiUhNzWmJMNXkafV02WDtCufWu83KUV?usp=sharing - It contains 3 .rar files: 1) Shape_1d_256i -> count = 1 diamond of each SHAPE label 2) Shape_5d_256i -> count = {'PS': 5, 'RA': 5, 'PR': 5, 'EM': 5, 'BR': 5, 'MQ': 5, 'SEM': 2, 'OV': 5, 'HS': 5, 'CMB': 5, 'PE': 3, 'RD': 5, 'TRI': 1, 'AS': 5} 3) Shape_10d_256i -> count = {'PS': 10, 'RA': 10, 'PR': 10, 'EM': 10, 'BR': 10, 'MQ': 10, 'SEM': 2, 'OV': 10, 'HS': 10, 'CMB': 10, 'PE': 3, 'RD': 10, 'TRI': 1, 'AS': 10}
## Tech Stack

**Client:** Python, NumPy, Pandas, OpenCV, Matplotlib, tqdm


## Installation

For windows : Open the command line terminal in your machine and do the following described.
To install NumPy:
```bash
  pip install numpy
```
To install Pandas:
```bash
  pip install pandas
```
To install os:
```bash
  pip install os-sys
```

To install OpenCV:
```bash
  pip install opencv-python
```

To install matplotlib:
```bash
  pip install matplotlib
```

To install tqdm:
```bash
  pip install tqdm
```

Once the necessary above installations are done, import all the necessary modules and the code would work.
    
## Description of libraries

### NumPy
NumPy is be used to perform a wide variety of mathematical operations on arrays. It adds powerful data structures to Python that guarantee efficient calculations with arrays and matrices and it supplies an enormous library of high-level mathematical functions that operate on these arrays and matrices.

### Pandas
Used for data analysis.

### OS
The OS module provides functions for interacting with the operating system.

### OpenCV
OpenCV is used for all sorts of image and video analysis, like facial recognition and detection, license plate reading, photo editing, advanced robotic vision, optical character recognition, and a whole lot more.

### Matplotlib
Matplotlib is a comprehensive library for creating static, animated, and interactive visualizations in Python.

## Roadmap

- First of all we need to run step by step by step code and set the file path according to your system else it will give FileNotFoundError , so set the path according to your system by downloading all the necessary images given in the folder in the project description . 
- After that input the number of the directory as per your wish and which images you want background to be removed. 
- After inputing the appropriate number,the images of that folder would be displayed with their background removed.



## Support

For support, email fake@fake.com or join our Slack channel.


## Custom functions used

- init_grabcut_mask : To find the mask of the images.
- add_contours : Used to find the contour of the selected images.This takes two parameters one is the image and second is the mask we derived from the previous function.
- remove_background : This is the function used to remove the background from the images.It takes the image as one parameter and two strings for the naming conventions of the images.
## In-built functions used

- cv2.GC_PR_BGD : A possible background pixel
- cv2.GC_PR_FGD : A possible foreground pixel
- cv2.GC_FGD : An obvious foreground pixel 
- plt.imshow : To show the image
- cv2.findContour() : used for extracting the contours from the image.
- cv2.drawContours(image, contour, -1, color, thickness) : used for drawing the cobtour and the color and thickness of it can be defined by us
Here in the add_contours() function we have defined a if condition so if the number of contours are not zero only then it will go inside the loop
- grabCut(img, mask, rect, bgdModel, fgdModel, iterCount[, mode]) ->mask, bgdModel, fgdModel

    Understanding it's parameters and what does it return:

    - img: The input image, which GrabCut assumes to be an 8-bit, 3-channel image (i.e., unsigned 8-bit integer in BGR channel ordering).
    - mask: The input/output mask. This mask is assumed to be a single-channel image with an unsigned 8-bit integer data type. This mask is initialized automatically if you use bounding box initialization (i.e., cv2.GC_INIT_WITH_RECT); otherwise, GrabCut assumes you are performing mask initialization (cv2.GC_INIT_WITH_MASK).
    - rect: The bounding box rectangle that contains the region that we want to segment. This parameter is only used when you set the mode to cv2.GC_INIT_WITH_MASK).
    - bgModel: Temporary array used by GrabCut internally when modeling the background.
    - fgModel: Temporary array used by GrabCut when modeling the foreground.
    - iterCount: Number of iterations GrabCut will perform when modeling the foreground versus background. The more iterations, the longer GrabCut will run, and ideally the results will be better.
    - mode: Either cv2.GC_INIT_WITH_RECT or cv2.GC_INIT_WITH_MASK, depending on whether you are initializing GrabCut with a bounding box or a mask, respectively.
    - OpenCV’s GrabCut implementation returns a 3-tuple of:

        - mask: The output mask after applying GrabCut
        - bgModel: The temporary array used to model the background (you can ignore this value)
        - fgModel: The temporary array for the foreground (again, you can ignore this value)

- cv2.cvtColor() : used to convert an image from one color space to another.
- cv2.COLOR_BGR2RGB : BGR is converted to RGB
- COLOR_BGR2LAB: used to change the BGR color space to LAB color space.
- cv2.createCLAHE : noise reduction
The above processes are done for color enhancement and better edge detection and after that the remove_background() function is called and the images are processed .

## Authors

- 19BCE229 Rushir Bhavsar (Leader)
- 19BCE238 Harshil Sanghvi [@harshilsanghvi](https://github.com/harshil-sanghvi) 
- 19BCE257 Ruju Shah
- 19BCE261 Vrunda Shah
- 19BCE185 Khushi Patel

