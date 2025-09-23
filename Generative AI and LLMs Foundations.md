#ai #notes 

# What is Generative AI

Generative AI is a subset of Deep Learning which uses existing data to create new data that shares the patterns of data. It can be used to generate data in multiple formats like text, image, audio and video.

# Types of Generative AI

- Text Based -> Learns from large amount of text and generates text, code, article, etc.
- Multimodal -> Learns from different kinds of data like text, video, audio etc and generates different kinds of data types like text, video, audio.

# Language Model

A language model is a probabilistic model of text that determines the probability of a given sequence of words occurring in a sentence based on the previous words. It helps to predict which word is more likely to appear next in the sentence.

So, given an input text with a blank space to fill in the next word, the language model will compute a probability distribution over a vocabulary. That means that the language model knows about a set of words that should appear in the blank space and will compute the probability of various words that can be filled in the blank space. Once the probabilities are calculated, the highest probability word is added to the blank space. There can be words and tokens like EOS (End of Sequence) for which the probability is calculated. If the EOS is determined as the largest probability, then a full stop is added.

When we run a sequence of words through a language model, we are going to get a probability for every single word in its vocabulary, but no words outside of its vocabulary.

These models are generally referred as Large Language Models because they have a large number of parameters, although there is no threshold agreed upon which decides whether a language model is large or small. Parameters are the adjustable weights in the neural network that are optimised during training to predict the next word in a sequence.

Large language models are based on a deep learning architecture called transformer. This allows them to pay selective attention to different parts of the input when making the next word prediction. This gives LLMs enhanced contextual understanding.

Having a large number of parameters does not necessarily translate to better performance on any given task. In fact, if a model is too large and has too many parameters, it can potentially overfit to the training data.
