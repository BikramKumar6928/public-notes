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

## Embeddings

Embeddings are numerical representation of a piece of text. The piece of text could be a word, could be a phrase, could be a sentence, could be a paragraph, or even one or more paragraphs. Embeddings make it easy for computers to understand the relationship between pieces of text.

## Encoder model

The encoder model take all the tokens of the input as an input and generates 1 embedding corresponding to each token. An additional embedding is created corresponding to the whole sentence. So the output of a encoder model is a list of tokens and the output is a list of vectors.

## Retrieval Augmented Generation (RAG)

The vector output of encoders can be used to perform a semantic search where vectors are generated from a corpus of data and stored in a vector database. When an input text is received, it is encoded to vectors and check the similarity of the encoded input against the similarity of each document in the database. And then you return the most similar or the most relevant document.

This similar data can be provided to an LLM which can then use the content and its general knowledge to provide an informed answer. This whole architecture is called Retrieval Augmented Generation or RAG.

## Decoder Model

Decoder model takes multiple tokens as input and outputs the next token in the sequence based on the probability of the vocabulary, which they compute. The decoder only produces a single token at a time. We can always invoke a decoder over and over to generate as many new tokens as we want, but always producing a single token at a time. This is achieved using self-referential loops.

## Encoder-Decoder Architecture

In this architecture, basically we glue a decoder into an encoder, so as you can see here. They have been primarily being utilised for sequence-to-sequence tasks, like translation. This then takes a sentence as an input. It breaks it into multiple tokens. The tokens are then encoded into vectors. These vectors are used as an input to the decoder which generates the output tokens one by one.

# Prompt Engineering

LLMs are geared towards text completion as they predict the next token in the input text. Because completion LLMs are trained to predict the next word on a large data set of internet text, rather than answering the question user asked. So you cannot give instructions or ask questions to a completion LLM. Instead, you need to formulate your input as a prompt whose natural continuation is your desired output.

## Prompt

Prompt is the input or initial text provided to the large language model. Text prompts are how users typically interact with large language models.

## Prompt Engineering

Prompt engineering is the process of iteratively refining a prompt for the purpose of eliciting a particular style of response.

## Instruction Tuning

Instruction Tuning is a critical step in LLM alignment. It involves fine-tuning a pre-trained LLM on a varied set of instructions, each paired with a desired output.

### Reinforcement Learning from Human Feedback (RLHF)

RLHF is a model training procedure that is applied to a fine-tuned language model to further align model behavior with human preferences and instruction following. So in this case, what we do is human annotators write prompts and compare the model outputs. The human feedback is subsequently used to train a reward model, which learns patterns in the preferences of the human annotators and can then automate preference decisions.

## Types of prompting

### In context learning

An LLM is conditioned with instructions or demonstrations of the task it is meant to complete. Note that it is not learning in the traditional sense as none of the parameters of the model are changing. What in-context learning means is that it has demonstrations of the tasks that the model is supposed to complete. An example of in context learning is K shot prompting.

#### K shot prompting

In this, when the LLM is given a prompt, the prompt contains examples of what the LLM needs to do. For example, if we want the LLM to translate some text, we would give the command to translate the text and give a K examples of sample translations. If the number of examples given is K, then it is called K shot prompting.

### Chain of Thought prompting

If you have a complicated task, then what we are going to do is we are going to prompt the model to break the problem into small chunks, exactly like you would solve it if you were solving it yourself, and then you break it into smaller parts, and then you solve each of these intermediate steps or each of these smaller parts.

So 