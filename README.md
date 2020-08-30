# Neural-Style-Transfer
by Yashaswi Yenugu


# What is Neural Style Transfer
Neural Style Transfer is a technique to blend two images - a *content* image and a *style* image - such that
the content image looks like it was painted in the style of the style image.
The blended image is called *generated* image.




# How is it Done?
The generated image is initially defined as the content image.
The *content* and *style* images are put into a neural network (VGG19 in this case) and the outputs from a particular layer are extracted by forward propagation.
Let the activations from the network for the *content (C) * and *generated (G) * images be ***a<sub>c</sub>*** and ***a<sub>c</sub>*** respectively.

Then we evaluate the *content cost* defined as follows:

![Test Image 4](https://i.imgur.com/lBx5NLa.png)

Similarly we evaluate the *style cost*. We need to introduce *Gram matrices* for this.
A Gram matrix of a set of vectors (v<sub>1</sub>,v<sub>2</sub> .... v<sub>n</sub>) is defined as:

![Test Image 4](https://i.imgur.com/R8QhI1W.png)
