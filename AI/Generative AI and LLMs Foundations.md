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

> The LLM provides the reasoning which it used to reach a logical point. This allows it to make sure that it does not make mistakes.

# Hallucination

Hallucination is basically means the model generated text that is non-factual and ungrounded. At times, statements that are nonsensical or factually incorrect are also considered to be hallucination.

Retrieval Augmented systems hallucinate less than 0-shot LLMs.


# Customising LLMs with custom data

It is possible that the LLM is not providing required information in a required format. There are 3 ways to customise LLM with custom data so that the responses are better

## Prompt Engineering

This is the quickest and fastest way to customise the LLM. Basically, the prompt is modified using techniques like K shot prompting to guide the LLM in providing responses based. This is helpful when the LLM already understands topics that are necessary for the text generation.

The drawback of using prompt engineering is that it adds latency to each request, as the prompts are injected for each input prompt.


## Retrieval Augmented Generation (RAG)

RAG can be used to hook the LLM with an enterprise knowledge base. This allows the LLM to respond with response which are more grounded in the knowledge base, so that it does not hallucinate much. This method can be used to fetch specific and exact information from the knowledge base, which may not be possible using just the model as it takes probabilistic guesses at next words. The LLM then uses the retrieved data to generate an informed response. Example:- Fetch the amount of money in user's account.

RAG should be used when the data changes rapidly and a need for exact information surrounded by text for people to understand exists. This is also good when we want to mitigate hallucinations by grounding answers in enterprise data.

The drawbacks are that this is more complex to setup as we need data stored in specific format. This also requires the data to be stored in a compatible format like vector database.
## Fine tuning

The LLM can be fine tuned if there is domain specific data. The LLM can learn on top of what it already knows (pre-trained data), thus allowing it to respond with domain specific or special skill that it has not already been trained upon. Fine tuning can also help when the response are required in a unique style in which the LLM does not responds by default. Fine tuning also becomes important when the data required to adapt the LLM is too large to be held in context along with input prompt, making prompt engineering to not work. It is also a good idea when the latency increases with LLM + prompt engineering.

A way of doing fine tuning is add additional hidden layers on top of the hidden layers of the LLM. The purpose of the new hidden layers is to transform the already trained LLMs output into the domain specific output that is populated during the fine tuning step. This method also completes the training faster as all the layers do not have to be updated in every iteration as compared to a process where all the layers are updated.

Once the training is done, the LLM is given prompt and the LLM generates output based on the knowledge it has learned during pre-training and fine-tuning.

The benefits of fine tuning are:-
- Improved Model Performance, as the model can better understand and generate contextually relevant responses.
- Improved Model Efficiency, as the number of trainable parameters are reduced thus making the model more efficient
- No impact on Model latency, as no prompt injection is happening for every prompts.

The drawbacks of fine tuning is that it requires a labelled dataset which can be expensive and time consuming to acquire.

## Workflow for customising LLMs with data

- Start with simple prompt for prompt engineering
- Add few shot prompting
- Add simple retrieval using RAG
- Fine-tune the model
- Optimise the retrieval on fine-tuned model
