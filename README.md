# Neural-Style-Transfer
by Yashaswi Yenugu


# What is Neural Style Transfer
Neural Style Transfer is a technique to blend two images - a *content* image and a *style* image - such that
the content image looks like it was painted in the style of the style image.
The blended image is called *generated* image.

The style image I have used is a painting called *Starry Night* by Vincent van Gogh

![Test Image 4](https://i.imgur.com/wy37mwH.jpg)




# How is it Done?
The generated image is initially defined as the content image.
The *content* and *style* images are put into a neural network (VGG19 in this case) and the outputs from a particular layer are extracted by forward propagation.
Let the activations from the network for the *content(C)* and *generated(G)* images be ***a<sub>c</sub>*** and ***a<sub>c</sub>*** respectively.

Then we evaluate the *content cost* defined as follows:

![Test Image 4](https://i.imgur.com/lBx5NLa.png)

Similarly we evaluate the *style cost*.
We need to introduce *Gram matrices* for this.
A Gram matrix of a set of vectors (v<sub>1</sub>,v<sub>2</sub> .... v<sub>n</sub>) is defined as:

![Test Image 4](https://i.imgur.com/R8QhI1W.png)

The *style cost* is defined as:

![test Image](https://i.imgur.com/oyWCW0S.png)

The entire cost function then would be defined like this:

![test Image](https://i.imgur.com/C7D6s0A.png)

Where alpha and beta are hyperparameters you need to tune.

Once the cost is evaluated (forward propagation) the network evaluates the derivative of the cost with respect to the generated image
and carries out backward propagation.
The procedure is summarised in the picture below:

![test Image](layout.png)

# Instructions

1. Download the images *content.jpeg* and *style.jpg*
2. Open the file *Neural_Style_Transfer.ipynb* and open it using google colab.
3. Switch the runtime type to 'GPU' for faster execution.
3. Run the cells and upload the images *content.jpeg* and *style.jpg* when asked by the notebook.
4. In case you want to upload your own images, you can do so. Change the hyperparameters accordingly.
5. Save the generated image.
