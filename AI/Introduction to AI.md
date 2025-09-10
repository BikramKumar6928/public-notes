
#ai #notes 

AI is capability of machines to mimic the cognitive abilities and problem-solving capabilities of human intelligence.
# Why is AI needed

AI is needed for:

- Automation and Decision Making
- Creative Support

## Types of AIs

- Normal AI -> Manipulates the input to get the output. Example -> Translating text
- Generative AI -> Generates stuff which is significantly different from input. Example -> Generating answer to questions

# AI Domains

- Language
- Vision
- Speech
- Product Recommendations
- Anomaly Detection
- Learn by Reward
- Forecasting
- Generate Content

# Language related AI tasks

Language AI tasks take text as input and perform various functions on them and gives output in same (like translate text) or different medium (like text to speech).
For Generative AI tasks, the output of the model is in text medium.

## Properties of text data

- The data is sequential. It means text cannot have multiple contexts going on in parallel
- The words in a text data must be broken into simpler terms called tokens so that it can be processed. The process is called tokenization.
- The sentences can be of different lengths. This is fixed by padding sentences so that they become of equal length.
- The similarity of text is found by performing dot or cosine similarity tests. This is also done through representation called embedding.

## Models used for processing text data

- Recurrent Neural Networks -> These process data sequentially and store hidden states
- Long Short-Term Memory -> These process data sequentially and can retain the context using gates
- Transformers -> These process data in parallel. These use concept of self-attention to better understand the context.

# Speech related AI tasks

These take audio as an input and perform various functions on them and gives output in same (like voice conversion) or different medium (like speech to text).
For Generative AI tasks, the output of the model is in audio medium.

## Properties of audio data

- Audio data is sampled at a particular rate which is called its sampling rate. This rate is generally at a frequency of 44.1kHz. This means the audio sample is taken 44,100 times every second to record it.
- The bit depth is the number of bits in each sample. It means how much data is gathered per sample.
- These samples must be processed in continuous groups in order to make any sense of data. As there is not much information in a single sample as it only contains data of an audio in the time duration of 1/44,100 second.

## Models used for processing audio data

The below models take into account the sequential nature of audio so that functions can be performed on them

- Recurrent Neural Networks -> These process data sequentially and store hidden states
- Long Short-Term Memory -> These process data sequentially and can retain the context using gates
- Transformers -> These process data in parallel. These use concept of self-attention to better understand the context.
- Variational Autoencoders
- Waveform Models
- Siamese Networks

# Image related AI tasks

These take image as an input and perform various functions on them and gives output in same (like repair damaged images) or different medium (like extract text in a image).
For Generative AI tasks, the output of the model is in image medium.

## Properties of image data

- Image data consist of pixels. Pixels are grid of data containing very small 2 dimensional information of an image. A pixel has a single colour.
- These pixels can be grey-scale or colour.

## Models used for processing audio data

- Convolutional Neural Networks -> These detect patterns in images, learning hierarchical representations of visual features.
- YOLO (You Only Look Once) -> Processes the image and detects objects within the image.
- Generative Adversarial Network -> Generates real-looking images.

# Anomaly Detection related AI tasks

These detect anomalies in time series data.

Example -> Fraud detection

# Recommendations related AI tasks

These categorises similar products or similar users together to recommend products to users

Example -> E-commerce websites

# Forecasting related AI tasks

These take time series data and makes predictions based on past data.
/commit
Example -> Weather forecasting
