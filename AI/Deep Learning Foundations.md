#ai #notes 

# What is Deep Learning

Deep learning is a subset of machine learning that focuses on training artificial neural networks to solve a task at hand. A very important quality of the ANN is that it can process raw data like pixels of an image and extract patterns from it.
# Benefits of Deep Learning

There is no need to provide them with what to look for in the data in contrast to Machine Learning where you have to specify what information should be looked at and what should be classified.

The data is understood by the ANN (Artificial Neural Network) by creating an internal representation, which is difficult to make manually.

Data Processing can be done in parallel, so large amount of data can be processed in a small amount of time.
# Deep Learning Data Types (with Examples and algorithms)

- images 
	- Example -> Image classification, Object detection -> CNN
	- Example -> Image Generation -> Transformers, GANs or diffusion models
- videos
- text -> Translate the text or detect the sentiment of a text -> Transformers, LSTM and RNN
- audio -> Music Generation, Speech-To-Text
# What is ANN

Artificial Neural Network is inspired by brain and neurons. They are made up of interconnected nodes called as neurons.

In ANN, we assign weights to the connection between neurons. Weighted inputs are added up. And if the sum crosses a specified threshold, the neuron is fired, and the outputs of a layer of neuron become an input to an another layer
## Building blocks of ANN

### Layers

The ANN is comprised of input layer, hidden layers and output layers. There can be >= 0 number of hidden layers in an ANN.
### Neurons

Neurons are computational units which accept an input and produce an output. 
### Weights

Weights determine the strength of connection between neurons.
### Activation function
 
Activation functions work on the weighted sum of inputs to a neuron and produce an output.
### Bias
Bias is an additional input to the neuron that allows a certain degree of flexibility.

## How are ANNs trained?

We use is the backpropagation algorithm. During training, we show an image to ANN. Let us say it is an image of digit 2. So we expect output neuron for digit 2 to fire. But in real, let us say output neuron of a digit 6 fired.

So what do we do? We know that there is an error. So to correct an error, we adjust the weights of the connection between neurons based on a calculation, which is called the backpropagation algorithm. By showing thousands of images and adjusting the weights iteratively, ANN is able to predict correct outcome for most of the input images. This process of adjusting weights through backpropagation is called as model training.

# Sequence Models

These models are good for processing sequential data. Sequential data is ordered list of data points or events.