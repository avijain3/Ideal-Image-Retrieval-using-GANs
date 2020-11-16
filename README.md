# Ideal-Image-Retrieval-using-GANs

Quick Reminder on Generative Adversarial Networks

 In Generative Adversarial Networks, two networks train against each other. The generator misleads the discriminator by creating compelling fake inputs. The discriminator tells  if an input is real or artificial.

There are 3 major steps in the training:

 Use the generator to create fake inputs based on noise

 Train the discriminator with both real and fake inputs

 Train the whole model: the model is built with the discriminator chained to the generator. The discriminator's weights are frozen in this step.

The Model

 The training process stays the same. First, let’s take a look at the neural network architectures!

The Generator

 The generator aims at reproducing sharp images. The network is based on ResNet blocks. It keeps track of the evolutions applied to the original blurred image

The Discriminator

 The objective is to determine if an input image is artificially created. Therefore, the discriminator’s architecture is convolutional and outputs a single value.

Losses

 We extract losses at two levels, at the end of the generator and at the end of the full model.

 The first one is a perceptual loss computed directly on the generator’s outputs. This first loss ensures the GAN model is oriented towards a deblurring task. It compares the   outputs of the first convolutions of VGG.

 The second loss is the Wasserstein loss performed on the outputs of the whole model. It takes the mean of the differences between two images
