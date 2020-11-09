# Sprint3

## Implementing saliency map

a saliency map is an image that shows each pixel‘s unique quality.

### Using saliency maps to visualize attention at MNIST inputs

the MNIST dataset. This dataset, which stands for Modified National Institute of Standards and Technology dataset, 
contains thousands of 28×28 pixel handwritten digits, like this:

![Image of MINST](https://www.machinecurve.com/wp-content/uploads/2019/07/mnist.png)

### Adding a Keras CNN

### Creating the saliency map

### The results

`Test loss: 0.03036452561810365 / Test accuracy: 0.9911999702453613`

![Image of MINST1](https://www.machinecurve.com/wp-content/uploads/2019/11/sal1.png)

![Image of MINST2](https://www.machinecurve.com/wp-content/uploads/2019/11/sal1-2.png)

![Image of MINST3](https://www.machinecurve.com/wp-content/uploads/2019/11/sal2.png)

![Image of MINST4](https://www.machinecurve.com/wp-content/uploads/2019/11/sal3.png)

![Image of MINST5](https://www.machinecurve.com/wp-content/uploads/2019/11/sal7.png)

![Image of MINST5](https://www.machinecurve.com/wp-content/uploads/2019/11/sal7-2.png)

![Image of MINST5](https://www.machinecurve.com/wp-content/uploads/2019/11/sal9.png)


### Using CIFAR10 inputs

![Image of MINST1](https://www.machinecurve.com/wp-content/uploads/2019/06/cifar10_visualized.png)

#### Result:

`Test loss: 0.8597345282554626 / Test accuracy: 0.7184000015258789`

![Image](https://www.machinecurve.com/wp-content/uploads/2019/11/airplane-2.png)
![Image](https://www.machinecurve.com/wp-content/uploads/2019/11/cat-2.png)
![Image](https://www.machinecurve.com/wp-content/uploads/2019/11/dog-2.png)
![Image](https://www.machinecurve.com/wp-content/uploads/2019/11/dog2.png)
![Image](https://www.machinecurve.com/wp-content/uploads/2019/11/frog-2.png)
![Image](https://www.machinecurve.com/wp-content/uploads/2019/11/horse-2.png)
![Image](https://www.machinecurve.com/wp-content/uploads/2019/11/truck-2.png)



# LSTM Model
We have so far etracted feature information from images, we will then conbine them with our questions by going through a LSTM (Long-Short-Term-Memory) model, the LSTM model will then compare the similarity of questions with features and generate answers. Since we only did our tesing in small amount of images, we have no enough features for training a LSTM model. Instead we implmented a sentiment analysis test using Kaggle dataset. In this test, we evaluated emotion setiment using Emoji. This test would be helpful for our future development as our Question related with emotions may occur. 

LSTM structure:
<img width="604" alt="Screen Shot 2020-11-04 at 11 44 52" src="https://user-images.githubusercontent.com/52185318/98141509-b2e0c480-1e94-11eb-8644-2d22e093afb5.png">

Emoji Q/A testing result:

<img width="575" alt="Screen Shot 2020-11-04 at 11 20 08" src="https://user-images.githubusercontent.com/52185318/98141671-defc4580-1e94-11eb-95f1-696d6160336a.png">




     


## Next Step

Train images in COCO Dataset.

Combining the saliency map into VQA model.

Expand current dataset

