# Natural-Language-Processing (NPL)
Natural Language Processing Repository for Text Classification, Sentiment Analysis, and Translation

Welcome to my Natural Language Processing (NLP) repository on GitHub! This repository is dedicated to developing models for various NLP tasks, including text classification, sentiment analysis, and translation projects.

Key Features

Text Classification and Sentiment Analysis:
I will develop models ranging from basic to complex for text classification and sentiment analysis tasks. Beginning with foundational approaches such as bag-of-words models, I will gradually introduce more advanced techniques, including sequential models such as recurrent neural networks (RNNs) and long short-term memory (LSTM) networks. These models will enable accurate and insightful classification and sentiment analysis of text data. In particular, I will implement the entire architecture of a transformer encoder to leverage its superior performance in capturing contextual information.

Translation Projects:
In addition to text classification and sentiment analysis, I will explore translation projects using sequence-to-sequence models. I will develop models that can effectively translate text from one language to another. For this task, I will implement the complete architecture of a transformer encoder-decoder, which has shown remarkable results in machine translation tasks. This will involve attention mechanisms and self-attention layers to capture important dependencies between words and generate high-quality translations.

Progressive Model Development:
The repository will follow a progressive model development approach. Starting with basic models, I will gradually introduce more complex architectures and techniques to enhance their performance. This incremental approach will enable a deeper understanding of the models and facilitate the exploration of advanced concepts in NLP.

Best Practices in Architecture:
Ensuring adherence to best practices in deep learning architecture design is a priority in this repository. I will incorporate the latest advancements in NLP research and industry standards to develop models that are not only accurate but also scalable and interpretable. By staying updated with the latest trends and techniques, I aim to create models that push the boundaries of NLP applications.

Join me on this exciting journey into the realm of Natural Language Processing. Together, we will explore text classification, sentiment analysis, and translation tasks, utilizing cutting-edge techniques and architectures to unlock the power of language understanding and generation.

## Bag-of-Words Model

The dataset used will be the **IMDB movie review sentiment-classification** dataset provided by Andre Maas at Stanford. 

 - [Using single word(unigrams)](https://nbviewer.jupyter.org/github/antirrabia/Natural-Language-Processing/blob/main/notebooks/BagOfWords(1-gram).ipynb) - With this approach, the TextVectorization layer will yield multi-hot binary vectors. The layer will consider individual words, discarding any order, and treat the reviews as set(bag) of tokens.

- [Using bigrams](https://nbviewer.jupyter.org/github/antirrabia/Natural-Language-Processing/blob/main/notebooks/BagOfWords(multi-hot-bigram).ipynb) - With this approach, we enhance our bag-of-words with a sense of local order by utilizing bigrams. Consequently, our layer will process bigrams (binary-encoded bags of bigrams) rather than single words.

- [Using bigrams(With tf-idf)](https://nbviewer.jupyter.org/github/antirrabia/Natural-Language-Processing/blob/main/notebooks/BagOfWords(tf-idf_bigram).ipynb) - With this approach, we will incorporate additional information by calculating the occurrence of bigrams, and we will further enhance the word counts by applying tf-idf normalization.


## Sequencial models
To implement a sequence model, we will start by configuring the layers.TextVectorization to return the movie reviews as sequences of integer indices (with each integer representing a single word). Next, we will convert each integer index into a vector using techniques like multi-hot encoding, word embedding, and self-attention within a transformer encoder. Finally, we will input these sequences of vectors into a stack of layers, including options like a 1D convnet, an RNN, or a Transformer.

- [Sequence Model(Multi-hot)](https://nbviewer.jupyter.org/github/antirrabia/Natural-Language-Processing/blob/main/notebooks/Sequence(one-hot_int).ipynb) - The most straightforward approach to converting each integer in the sequence into a vector is through multi-hot encoding. This results in a matrix with dimensions of 600 (words in a review) by 20,000(which is the dimension of each binary vector representing every possible word). However, this method is not recommended due to its inefficiency. Additionally, using a one-hot encoder implies to the model that each word in the review is independent from the others, which is not accurate.

- [Sequence Model(Word-embedding)](https://nbviewer.jupyter.org/github/antirrabia/Natural-Language-Processing/blob/main/notebooks/Sequence(WordEmbedding).ipynb) - A more robust approach involves training a layers.Embedding layer to obtain a vector representation for each word. This method is both more efficient and accurate. It is more efficient because it generates dense vectors with a dimension of 256, as opposed to the previous example's 20,000. Moreover, it is more accurate because each vector resides in a vector space that captures the semantic relationships between words, creating a consistent set of relationships with every other word in the space.

- [Sequence Model(Pretrained Word-Embedding)](https://nbviewer.jupyter.org/github/antirrabia/Natural-Language-Processing/blob/main/notebooks/Sequence(PretrainedWordEmbedding).ipynb) -   
