# [Kaggle Fake News](https://www.kaggle.com/c/fake-news/overview)
## To build a system to identify unreliable news articles
### Data Description
* id: unique id for a news article
* title: the title of a news article
* author: author of the news article
* text: the text of the article; could be incomplete
* label: a label that marks the article as potentially unreliable
  * 1: unreliable
  * 0: reliable

The data can be downloaded from Kaggle website using the above link
### Evaluation Metric
* The evaluation metric for this competition is accuracy, a very straightforward metric.
* Accuracy measures false positives and false negeatives equally, and really should only be used in simple cases and when classes are of (generally) equal class size
### Approach
* Missing Values are present in the data and are filles with the text "Unavailable". (If you know any better method to impute missing values in NLP, please share it)
* Text data is cleaned by removing punctuations and made consistently lower cased
* Code block to apply Lemmatize is commented as it is taking immense amount of time to implement this.
* Applied word embedding technique to the title column and also can be implemented by combining all the features in to a single feature. (Any comments about this would be apprecaited)
* Trained the model with LTSMs (includes Bidirectional) with Stochastic Gradient Descent optimizer as it started performing really well after 10-15 epochs whereas Adam also performed well from the first epoch but no significance increase in perfomance was seen
* Decision Boundary to classify predictions is based on threshold which maximizes ROC AUC however a threshold to maximize accuracy can also be developed
### Results
* Pulic Score: 92.7%
* Private Score: 93.6%
