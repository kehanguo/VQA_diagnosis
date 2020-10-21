# Sprint2
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

- localization layer
