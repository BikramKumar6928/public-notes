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

These models are good for processing sequential data. Sequential data is ordered lists of data points or events.

Some common examples of the sequence models are in natural language processing, deep learning models are used for tasks such as machine translation, sentiment analysis, or text generation. In speech recognition, deep learning models are used to convert recorded audio into text. And deep learning models can generate new music or create original compositions.

Even sequences of hand gestures are interpreted by deep learning models for applications like sign language recognition. In fields like finance or weather prediction, time series data is used to predict future values.

# RNN

Recurrent Neural Networks, abbreviated as RNN, are a class of neural network architectures specifically designed to handle sequential data. Unlike traditional feedforward neural network, RNN have a feedback loop that allows information to persist across different time steps. The key features of RNN is their ability to maintain internal state, often referred to as a hidden state or memory, which is updated as the network processes each element in the input sequence. The hidden state is then used as input to the network for the next time step, allowing the model to capture dependencies and patterns in the data that are spread across time.

> It takes the inputs as well as it's previous hidden state, thus allowing it to remember the past input.

Has multiple types like one-to-one, one-to-many, many-to-one and many-to-many depending on the number of inputs it takes and outputs it produces.

## Drawbacks of RNN

Since it just takes the previous state, it cannot distinguish what information is more important and thus gives same weightage to important and unimportant data. This phenomenon is also called vanishing gradient problem.

This happens because the previous information can be used by multiplying it with der

# Long Short-Term Memory (LSTM)

It contains specialized memory cells that it uses  to capture long-term dependencies in sequential data, enabling it to selectively remember and forget information over time, enabling the model to maintain relevant information over long sequences, which helps overcome the vanishing gradients problem.


