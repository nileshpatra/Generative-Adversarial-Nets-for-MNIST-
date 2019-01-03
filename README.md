# Generative-Adversarial-Nets-for-MNIST-
This repository contains a basic implementation of Generative Adversarial nets on MNIST dataset
implemented in keras.
The steps followed were :

```generator```
- A generator was initialized with a dense layer which would take up the noise
- A LeakyReLU activation was applied which trains the nets most efficiently
- Fianlly it returns a new Image

```discriminator```
- A discrimintaor was setup as a normal artificial neural network
- Appropriate activation functions were added

```makegan```
- The generator and discriminator were combined in the sequential layer

```preprocess```
- The preprocess function reshapes the 28X28 image to a 784 array and then the array is fed into the network.

  `reprocess```
- This function reprocesses the generated model to a 28X28 image again

```make_labels'```
- returns a series of numpy arrays of 0 and 1 for making output for real dataset and fake dataset

```the training : ```
- appropriate epochs are chosen
- the value of '''n_input''' i.e the random vector is 100
- learning rates for gan and discriminator are set accordingly
- at first discriminator is trained to recognize fake images and real images in the dataset
- the discriminator is then made untrainable for training the generator network
- the gan is then trained to generate better and better outputs for maintaining predicted output to be always 1.
- in each epoch losses are calculated and then appended

```plotting```
- after the training ends , mages are produced using noise and the generator
- the generator produces the image from noise
- the roduced images would be ofcourse 784 long 2D array
- we need to reshape it using the reprocess function defined above
- the images are finally plotted to get the generativr models

Note : The generative models are not very accurate and distinct because it has been trained on a relatively simple network.
Better lot of images can be obtained by using ```DCGANs```
