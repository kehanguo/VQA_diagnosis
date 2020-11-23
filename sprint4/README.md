# sprint4
In sprint3, we examined Saliency map method, in which the brightness of a pixel represents how salient the pixel is.This method is very useful to deal with big image where only a small part is needed predict the output. In our proposal, we are dealing with medical image(especially radiology images), this saliency map ideally will serve pretty good to extract features from region of interest, and we are still exploring its application in medical image field. Maybe in the later, we could implement this model with our current one.

<img width="406" alt="Screen Shot 2020-11-23 at 10 49 29" src="https://user-images.githubusercontent.com/52185318/99983282-a9eb6080-2d79-11eb-8fbf-2685599f6960.png">


## Multimodal Compact Bilinear Pooling (MCB)
In this sprint, we build our model on top of Multimodal Compact Billinear Polling(MCB).MCB uses a multimodal
compact bilinear pooling method that first predicts attention visually and textually then combines these features with question representation. MCB includes three components: a CNN image model, an LSTM question model, and MCB pooling that first predicts the spatial attention and then combines the attention representation with the textual representation to predict the answers.

For the image model, we used ResNet-152 pre-trained on imageNet. For the question model, a 2-layer LSTM model was used.

For our VQA system, we extract image features by using a  two 152-layer residual network,the output is a 2048 image feature vector, and then going to the MCB.It uses two CNNs to extract features from an image and combine the resulting vectors using an outer product, which is fully connected to an output layer,this will allow all elements of both vectors to interact with each other in a multiplicative way to increase accuracy. However, it'll increase the dimensionality to a crazy level. If we took vector n1=n2=2048 and each has 3000 features, they the total parameters would be 2048 * 2048 * 3000, eqaul to 1.25 billions. This would cost huge computation, so in MCB, usually the outer product will be projected to lower dimension to avoid computaion comsumption. 

Similarly, we use a 2-layer LSTM model to get our word features vector of size 2048. Those two vectors are going through anther MCB pooling layer.

<img width="919" alt="MCB" src="https://user-images.githubusercontent.com/52185318/99978173-9dfca000-2d73-11eb-82d4-0c9f87b27bf2.png">
Attention: To incorporate spatial information, we use soft attention on our MCB pooling method. we use MCB pooling to merge the slice of the visual feature with the language representation. As depicted in Figure 3, after the pooling we use two convolu-tional layers to predict the attention weight for each grid location. We apply softmax to produce a nor- malized soft attention map. We then take a weighted sum of the spatial vectors using the attention map to create the attended visual representation.



<img width="826" alt="Screen Shot 2020-11-23 at 12 16 07" src="https://user-images.githubusercontent.com/52185318/99993601-e45afa80-2d85-11eb-859c-1e0b27537726.png">





## Stacked Attention Networks(SAN)

The SAN model is a stacked attention model that queries images multiple times to progressively narrow an attention. Similarly to MCB, SAN includes three components: the image model based on a CNN to extract high level image representations, the question model using an LSTM to extract a semantic vector of the question and the stacked attention model which locates the image regions that are relevant to answer the question. We used the last pooling layer of VGG-16 pre-trained on imageNet as image features, and the last LSTM layer as question features. The image features and the question vector were used to generate the attention distribution over the regions of the image.

<img width="482" alt="SAN" src="https://user-images.githubusercontent.com/52185318/99978471-fcc21980-2d73-11eb-9b41-50c5fb786b68.png">

## System Architecture
<img width="928" alt="system_architecture" src="https://user-images.githubusercontent.com/52185318/99978178-9fc66380-2d73-11eb-9b01-644d8843b1be.png">

## Training output
Dataset: VQA_Rad dataset

<img width="874" alt="training_output" src="https://user-images.githubusercontent.com/52185318/99978196-a359ea80-2d73-11eb-8b46-9ec0c381d06d.png">

## Sprint5
we will try to combine our current model with saliency map/ stacked attention network to compare the performance.
