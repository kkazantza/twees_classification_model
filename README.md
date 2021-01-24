# Tweets Classification
The approach presented in the current project is used for a tweet classification task with 15 classes, and is based on two different Supervised Classification Techniques.

### 1D CNN for Text-Based Features
The 1st one implements a Convolutional Neural Network (or CNN) that uses as input word Embeddings that capture semantic relationships by creating vectors for each word of the posts in the training set.In this approach, the posts are pre-processed, tokenized and then represented with pre-trained word vectors that were already trained using fastText on Common Crawl.

### MLP Model for Graph-Based Features
The 2nd method implements a Multilayer Perceptron (or MLP) with input data vectors extracted from the graph which represents the users that made the tweets, with edge weights based on the retweets among the users.In this case, the Deepwalk algorithm is used in order to learn representations of the graph's vertices, and then a word2vec model is trained using skip-gram algorithm with input the final deepwalk vectors.

### Data Pre-Processing
* Cleansing
* Tokenization

### Feature Engineering
* Use of pre-trained word embeddings
* Extra information is added to the embedding matrix using polarity and subjectivity scores from the TextBlob python package.

### Submission Model

1. Averaging Ensemble Model

After the training phase of the above two models on the same dataset we took the average over their predictions.
**Averaging Test Loss: 0.90598**

2. Stacking Ensemble Model

The Averaging Model can be improved by weighting the contributions of each sub-model to the combined prediction by the expected performance of the sub-model. This can be extended further by training an entirely new model to learn how to best combine the contributions from each sub-model. This approach is called stacked generalization.
**Stacked Test Loss: 0.864**
