# Fast-Neural-Style-Transfer
A PyTorch implementation of the fast neural style transfer as proposed by [Johnson et al.](https://arxiv.org/abs/1603.08155)

## Style Image
The Great Wave of Kanagawa by Hokusai

![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/style_image/great_wave.jpg)


## Stylized output
![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_14.png) ![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_9.png)
![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_10.png) ![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_12.png)
![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_17.png) ![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_13.png)

I made use of the MS COCO dataset ‘2017 test images’ which is a dataset consisting of about 10 000 random images. The images obtained from this dataset were then treated as the set of content images to train the image transformation network. I used a batch size of 4 and trained the model for 1 epoch.

The fast neural style transfer makes use of two models to accomplish the task of stylizing a given image. It consists of the aforementioned image transformation network and another pre-trained image classification model to extract specific features of both the style and content image. I opted for the VGG19 as my pre-trained model in this scenario. At first during training a content image is passed on to the image transformation network to obtain the transformed image. In the transformation process the content image will be down-sampled from its original size through a series of convolutional and max pooling layers, and finally up-sampled to its original size through transpose convolutional layers.

Then both the content and the transformed content image are fed into the VGG19 model to extract certain feature maps from specific layers. Thereafter the loss of the transformation network will be computed based on the content and style loss. 

Similar to neural style transfer brought forward by [Gatys et al.](https://arxiv.org/abs/1508.06576) the fast neural style transfer model has two important hyper-parameters which govern the extent to which the content image is stylized. They are the content and style weights. These two hyper-parameters will be used to give weightage to the content and style loss respectively.Then the image transformation network will be optimized based on the weighted sum of the two losses. I chose 1 and 12 as my content and style weights and used the Adam optimizer with a learning rate of 0.001.

## Attributions
* Perceptual Losses for Real-Time Style Transfer and Super-Resolution by [Johnson et al.](https://arxiv.org/abs/1603.08155)
* Rusty Mina's [fast-neural-style: Fast Style Transfer in Pytorch!](https://github.com/rrmina/fast-neural-style-pytorch)

