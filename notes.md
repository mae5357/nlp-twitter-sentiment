# NLP

## packages

### NLTK
NLTK is specialized on gathering and classifying unstructured texts. If you need e.g. a POS-tagger, lemmatizer, dependeny-analyzer, 

- good for preprocessing
- good for tokenization

### Gensim

- word2vec
- topic modeling and document similarity


## Preprocessing

- stop words
- stemming/lemma
- lower-case

## Tokenization

https://machinelearninggeek.com/explore-python-gensim-library-for-nlp/#Create_Gensim_Dictionary
- list of models 

### Bag of Words

In Term Frequency(TF), you just count the number of words that occurred in each document. The main issue with this Term Frequency is that it will give more weight to longer documents. Term frequency is basically the output of the BoW model.

### TF-IDF

TF-IDF is the product of two statistics, term frequency and inverse document frequency. The term frequency is the same as BoW, but the inverse document frequency is the log of the ratio of the total number of documents to the number of documents with the term in it. This is done to give more weight to terms that are rare across all documents.

### Word2Vec

- Continuous Bag of Words (CBOW) predicts the current word based on four future and four history words. (from 4 words predict 1 word)
- Skip-gram predicts the surrounding words based on the current word. (from 1 word predict 4 words)

### FastText

- FastText is an open-source, free, lightweight library that allows users to learn text representations and text classifiers. It works on standard, generic hardware. Models can later be reduced in size to even fit on mobile devices.
- FastText is an extension of Word2Vec. It can predict on unseen words


### GloVe

GloVe is an unsupervised learning algorithm for obtaining vector representations for words. Training is performed on aggregated global word-word co-occurrence statistics from a corpus, and the resulting representations showcase interesting linear substructures of the word vector space.

## Models

https://www.machinelearningplus.com/nlp/gensim-tutorial/#8howtocreatethetfidfmatrixcorpusingensim

## Topic Modeling

### LDA

- bag of words -> tf-idf -> LDA
- LSA learns latent topics by performing a matrix decomposition on the document-term matrix using Singular value decomposition. LSA is typically used as a dimension reduction or noise-reducing technique.

## Vocab

```dictionary = corpora.Dictionary(texts)```
Before proceeding, we want to associate each word in the corpus with a unique integer ID.

## bag of words

```
bow_corpus = [dictionary.doc2bow(text) for text in processed_corpus]
pprint.pprint(bow_corpus)
```

[[(0, 1), (1, 1), (2, 1)],
 [(0, 1), (3, 1), (4, 1), (5, 1), (6, 1), (7, 1)],
 [(2, 1), (5, 1), (7, 1), (8, 1)],
 [(1, 1), (5, 2), (8, 1)],
 [(3, 1), (6, 1), (7, 1)],
 [(9, 1)],
 [(9, 1), (10, 1)],
 [(9, 1), (10, 1), (11, 1)],
 [(4, 1), (10, 1), (11, 1)]]