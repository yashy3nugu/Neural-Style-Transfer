# Neural-Style-Transfer
by Yashaswi Yenugu


# What is Neural Style Transfer
Neural Style Transfer is a technique to blend two images - a *content* image and a *style* image - such that
the content image looks like it was painted in the style of the style image.
The blended image is called *generated* image.

NST was first published in the paper "A Neural Algorithm of Artistic Style" by Gatys et al., originally released to ArXiv 2015

The style image I have used is a painting called *Starry Night* by Vincent van Gogh.
The content and style images are uploaded onto this repository

![content and style](https://i.imgur.com/wy37mwH.jpg)




# How is it Done?
The generated image is initially defined as the content image.
The *content* and *style* images are put into a neural network (VGG19 in this case) and the outputs from a particular layer are extracted by forward propagation.

Let the activations from the network for the *content(C)* and *generated(G)* images be ***a(c)*** and ***a(g)*** respectively.

Then we evaluate the *content cost* defined as follows:

![content cost equation](https://i.imgur.com/oVBHAqP.png)

Similarly we evaluate the *style cost*.
We need to introduce *Gram matrices* for this.
A Gram matrix of a set of vectors (v<sub>1</sub>,v<sub>2</sub> .... v<sub>n</sub>) is defined as:

![Gram matrix](https://i.imgur.com/R8QhI1W.png)

An important feature of the Gram matrix is that the value G<sub>ij</sub> measures how the activations of filter i is similar to the activation of the filter j.
This is an important factor in style transfer.

![correlation](https://i.imgur.com/RHdHYuo.png)

Then the *style cost* for the *generated(G)* and *style(S)* images is defined as:

![style cost equation](https://i.imgur.com/oyWCW0S.png)

The entire cost function then would be defined like this:

![cost function equation](https://i.imgur.com/C7D6s0A.png)

Where alpha and beta are hyperparameters you need to tune.

Once the cost is evaluated (forward propagation) the network evaluates the gradient of the cost with respect to the generated image
and carries out backward propagation.
The procedure is summarised in the picture below:

![network layout](layout.png)

# Instructions

1. Download the images *content.jpeg* and *style.jpg*
2. Open the file *Neural_Style_Transfer.ipynb* and open it using google colab.
3. Switch the runtime type to 'GPU' for faster execution.
3. Run the cells and upload the images *content.jpeg* and *style.jpg* when asked by the notebook.
4. In case you want to upload your own images, you can do so. Change the hyperparameters accordingly.
5. Save the generated image.

# Update
This is another set of content and style images to which neural style transfer has been applied using the model in the notebook

![test Image](https://i.imgur.com/fHonY74.jpg)
