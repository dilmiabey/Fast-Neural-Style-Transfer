# Fast-Neural-Style-Transfer
A PyTorch implementation of the fast neural style transfer as proposed by [Johnson et. al.](https://arxiv.org/abs/1603.08155)

## Style Image
![The Great Wave of Kanagawa by Hokusai](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/style_image/great_wave.jpg)


## Stylized output
![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_14.png) ![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_9.png)
![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_10.png) ![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_12.png)
![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_17.png) ![](https://github.com/dilmiabey/Fast-Neural-Style-Transfer/blob/master/test_results/output_13.png)

I made use of the MS COCO dataset ‘2017 test images’ which is a dataset consisting of about 10 000 random images.The images obtained from this dataset were then treated as the set of content images to train the image transformation network. I used a batch size of 4 and trained the model for 1 epoch.
This implementation makes use of the pre-trained VGG-19 model. Further 'Adam' is used as the optimzier for the image transformation network with a learning rate of 0.001. The content and style weights used for this project are 1 and 12 respectively.

## Attributions
* [Perceptual Losses for Real-Time Style Transfer and Super-Resolution](https://arxiv.org/abs/1603.08155)
* Rusty Mina's [fast-neural-style: Fast Style Transfer in Pytorch!](https://github.com/rrmina/fast-neural-style-pytorch)

