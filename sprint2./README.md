# Sprint2
# image processing
Firstly, we explored several ways to do image processing using machine learning. Here we will demonstrate two major algorithm that we did in this sprint.
##  Image classification

Here we implemented a simple transfer learning model to classify ants and bees. The training set has been properly cut. We have nearly 120 images in total for traning, and 75 images for validation. This test could be run in CPU easily, and takes about 25 minutes overall. The reason we choose to run this model is to better understand how image is processed in convulutional neural network. It is simply a tutorial for us to get familiar with torch. And the result is showed below:

<img width="1194" alt="Screen Shot 2020-10-19 at 11 20 12" src="https://user-images.githubusercontent.com/52185318/96671515-efa6aa80-132f-11eb-87b8-05d9aa518d0b.png">

## Denscap model 
We are planning to build our project on top of Denscap model developed by Standford University. This model implement a fully convolutional localization networks for Dense Captioning (FLCN).

<img width="868" alt="Screen Shot 2020-10-21 at 00 01 56" src="https://user-images.githubusercontent.com/52185318/96671807-b91d5f80-1330-11eb-8c5a-4b0a157dfb8a.png">

We will go through this model step by step:
- VGG16 architecture: VGG-16 is a network that contains 16 layers.It consists of 13 layers of 3 × 3 con-
volutions interspersed with 5 layers of 2 × 2 max pooling. In this model, the final pooling layer is replaced by a fully convolutional cocalization Layer.

<img width="902" alt="Screen Shot 2020-10-21 at 10 05 42" src="https://user-images.githubusercontent.com/52185318/96731976-da5c6b00-1385-11eb-9c5d-5d4c5bfb63d6.png">

- localization layer: The localization layer accepts a tensor of activations, then internally selects B regions of interests. In this process, three outputs will be generated: Region Coordinates, Region Scores, Region Features.  For each region, the size of feature vector is varying, so the output would go through a bilinear interpolation to sample those features to the same size. So far, the processing of image is completed in this system.

<img width="1008" alt="Screen Shot 2020-10-21 at 10 14 37" src="https://user-images.githubusercontent.com/52185318/96732428-4fc83b80-1386-11eb-9584-91a870f7e3d5.png">

### build the system
For our own VQA project, we want to duplicate the image processing the same way as the Denscap model did so. So we tried to implement the repo in our own computer, for dataset, we use VisualGenome https://visualgenome.org as mentioned in the paper. And we are glad that we could produce a result. Here, we also break our traning data into a small dataset for saving computation but it still takes like an hour to train. And the result is shown below:
<img width="494" alt="Screen Shot 2020-10-21 at 10 34 06" src="https://user-images.githubusercontent.com/52185318/96735301-6d4ad480-1389-11eb-93ea-c66d2a9cadcd.png">

As we are doing medical image analysis, ideally we could implement this model to precisely seperate regions properly in a CT scan or sort the unhealthy tissues out among regular groups. This is merely our approach for now, and we also browsed some interesting repo that specifically focused on medical image analysis like NiftyNet that we might do some research later. https://github.com/NifTK/NiftyNet

# Image captioning
This is our step forward to image processing, we wanted to label each region with an captioning. In the Denscap model, and LSTM network is used as solution, but we do not have enough time to implement it for now. So, we chose an easy alternative to understand how image cpationing works. 
- Algorithm steps:

       Preparation 

Preprocess the images using InceptionV3. 

1  First, converting the images into InceptionV3’s expected format

2 Resizing the image to 299px X 299px
3 Normalizing the images (pixels from -1 to 1)
4 Initialize InceptionV3 and load the pretrained Imagenet weights. 

The shape of output layer is 8*8*2048. 
Caching the features extracted from InceptionV3

We can preprocess each image with InceptionV3 and cache the output to disk. 


- Preprocessing

Preprocess and tokenize the captions

1 First, we can tokenize the captions, splitting them into words.(by space)

2 Second, constrain the size of vocabularies to 5000 words (save memory). Replacing all the other words with the token “UNK”

3 Third, we can create word to index and index to word mappings. 

4 Last, padding all sequences to be the same length as the longest one. 

# Split training data and testing data.  

Modeling

Extracting features from lower convolutional layer of InceptionV3 (8,8,2048)
Squashing it to (64,2048)
Then passing it to CNN Encoder (Fully connected layers)
RNN attends over the image to predict the next word. 


### Extracted features -> Encoder -> hidden state -> decoder -> prediction - > calculating loss-> using Teacher forcing to decide the next input to the decoder -> calculating the gradients and apply it to the optimizer and backpropagate 


<img width="640" alt="Screen Shot 2020-10-21 at 10 50 34" src="https://user-images.githubusercontent.com/52185318/96737225-6ae97a00-138b-11eb-9bc8-631279e10aeb.png">
<img width="867" alt="Screen Shot 2020-10-21 at 10 50 19" src="https://user-images.githubusercontent.com/52185318/96737238-6f159780-138b-11eb-9a80-ce9241c7f36a.png">

## Step forward
In sprint 3, we will try to do the following:
- optimaze the performance by enlarging training dataset, this might be done one SCC.
- connect the result of image processing with a LSTM network to do image captioning.


# Reference:
https://cs.stanford.edu/people/karpathy/densecap.pdf
https://visualgenome.org/VGViz/explore?query=zebra
https://github.com/abhshkdz/neural-vqa/blob/master/README.md

