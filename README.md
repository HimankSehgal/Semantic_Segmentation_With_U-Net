# Semantic_Segmentation_With_U-Net

## Table of Contents: 
* Overview of Project

* Data Description 
* Libraries used

* Steps followed

* Conclusion



## Overview of Project:

We are given Helen Dataset which contains images of faces of different persons. Our target is to classify each pixel as 
* bg   (background)

* face 
* lb  (left brow)

* rb (right brow)
* le  (left eye)
  
* re (right eye)

* nose
* ulip
* imouth
* llip
* hair 

## Data Description:   
For this project , the Helen Dataset used can be downloaded from <a href='https://drive.google.com/file/d/1jweX1u0vltv-tYZhYp6mlyDZDy0aDyrw/view?usp=sharing'>Helen Dataset</a>.<br>
For each image. It has 3 types of files. One is image.jpg which has the file which will be loaded to the model. Second is the label.png file which has all pixel by pixel classications of the image. The viz.jpg file is just for demonstation purpose and is not of any use to the model.<br>
Following is the directory structure 


<pre>.
└── helenstar_release
     ├── train
     │   ├── image.jpg
     │   ├── label.png
     ├   ├── viz.jpg
     │   └── ... (1999 sets of 3 images i.e 5997 images total)           
     └── test
         ├── image.jpg
         ├── label.png
         ├── viz.jpg
         └── ... (100 sets of 3 images i.e 300 images total)</pre>

Total number of images in dataset : 2099<br>
Number of images in train set : 1999<br>
Number of images in test set : 100


For convenience I will be performing some shiftings to put all image.jpg files in one folders , label.png in other. I will be doing this using the <tt>shutil</tt> module of python

The final directory strucutre will be as follows
<pre>.
└── splitted_Data
        ├── train
        │   ├── images
        │   │   ├── image1.jpg
        │   │   ├── image2.jpg
        │   │   └── ... (1999 files)
        │   └── labels
        │       ├── label1.jpg
        │       ├── label2.jpg
        │       └── ... (1999 files)       
        │           
        └── test
            ├── images
            │   ├── image1.jpg
            │   ├── image2.jpg
            │   └── ... (100 files)
            └── labels
                ├── label1.jpg
                ├── label2.jpg
                └── ... (100 files)</pre>
                
Sample image.jpg file - -----------------------------------------------------------------------------

Samoke label.png file  -----------------------------------------------------------------------------------

## Libraries used:
* Numpy

* Matplotlib

* torch
* torchvision<br>
  
* PIL

* os module of python
* tqdm

## Steps Followed

* ### 1. Importing Necessary Libraries
Getting all the required python libraries required for the implementation of the project

 
* ### 2. Looking at directory structure and making desired shiftings
As shown above, the directory strucutre in the link is changed so that it is easy to execute in the later part


* ### 3. Data Preprocessing
Now all the images have different dimensions. But to feed them into the model, all the images need to be of the same size. I resized all the images to 256x256. Also when we load images , they are usually loaded in the form of numpy array with <tt>dtype = uint8</tt> . They need to be converted to tensors with <tt>dtype = torch.float32</tt>

* ### 4. Defining Train and Test Dataloaders
Now the train dataset has 1999 images which can not be fed in one go. I use <a href='https://drive.google.com/file/d/1jweX1u0vltv-tYZhYp6mlyDZDy0aDyrw/view?usp=sharing'>Mini Batch Gradient Descent</a>.


* ### 5. Defining model



* ### 6. Defining Dice Loss and optimizer


* ### 7. Performing Forward Propagation


* ### 8. Visualizing train loss


* ### 9. Visualizing predictions



## Conclusion

Wo F1 score waala daal dena
