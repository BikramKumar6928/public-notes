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

## Transformers

Transformer is an algorithm that is used for sequential data. It has the capability of looking at all the words at the same time, thus allowing it to not forget about words which are separated far apart in a sentence.

RNNs can be used for sequential data, but the disadvantages of RNNs are that they cannot retain context of words which are separated from each other due to vanishing gradients problem. RNNs can only capture dependencies of nearby words.

There is a mechanism in the transformer architecture known as self-attention mechanism. The mechanism adds context to the text. The self-attention mechanism that allows the model to weigh the importance of different words or tokens in a sequence relative to each other. This mechanism enables the model to capture long-range dependencies and contextual relationships within the input data, enhancing its ability to understand the context.

The transformer architecture has two submodules -> an encoder and a decoder. The encoder module processes the input text and encodes into a series of numerical representations, also referred to as vectors (also called embeddings) that capture the contextual information of the input. And then the decoder module takes these encoded vectors and generates the output text.

Both the encoder and the decoder consist of many layers connected by the self-attention mechanism.

## Tokens

A token is the smallest part of an input that an LLM can understand. A token can be a word. It could be an entire word. It could be part of a word or it could even be a punctuation symbol. A common word, such as apple, is a token. A word such as friendship is made up of two tokens, friend and ship. The number of tokens per word depend on the complexity of the text. For simple text which have simple words, you can assume one token per word on average. For complex text which have fewer common words, you can assume two to three tokens per word on average.

