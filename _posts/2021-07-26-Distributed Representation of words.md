---
published: true
---
The Word2Vec is an algorithm that can find similarities and differences from words in NLP(Natural Language Processing) task. With word vectors we can easily find similarities or dissimilarities using distance measures(such as [Euclidean distance](https://en.wikipedia.org/wiki/Euclidean_distance)).

But how we can represent words in vector space?

For representing words in vectors we have two options:

1 - One-hot

2 - Word Embedding(note it's not only for words)


## One-hot

|![_config.yml]({{ site.baseurl }}/images/Word2vec/one_hot.png)|
|:--:| 
| Figure 1: One-hot|

As you can see in figure 1 every word in this sentence is represented as a vector with size 8(our vocab size) which only the index of the corresponding word is 1 and the other words are 0. But this approach makes words independent of each other and obviously, this would be a bad idea to find similarities or differences.
For instance, if we dot product **ate** vector and **played** vector together we would get 0 and this means they don't have any similarities, but in fact, at least they have a similarity, they are both simple past.

## Word Embedding

|![_config.yml]({{ site.baseurl }}/images/Word2vec/embedding.png)|
|:--:| 
| Figure 2: Word Embedding|

Word Embedding is more complex than one-hot. In this approach, the word would be present as a vector with Embedding dimension **N**(in figure 2 it's 4) that feeds with random numbers at the beginning. The numbers that constructed embedding vector are updating every step as same as the model's weights. For a better understanding of the embedding concept, imagine we have a word like **computer** that feeds with an embedding vector with dimension 100 then every number in this embedded vector describes one feature of computer like noun, singular and etc.