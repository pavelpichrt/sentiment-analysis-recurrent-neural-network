# Text classifier for Sentiment analysis using a Bi-directional Recurrent Neural Network

![RNN - description](https://s3.eu-west-2.amazonaws.com/pavdev.io/nlp/rnn.png)

## Introduction

Recurrent neural networks (RNNs) were introduced in the 1990s in response to a variety of challenging problems, including motion detection, temporal sequences of events, and ordered data, such as characters in words [1]. As part of ongoing research, Schuster and Kuldip (1997) introduced the idea of bidirectional communication between the hidden layers of an RNN. Such a network can be trained simultaneously in both positive and negative time directions, removing the constraint of using input information only up to a predefined future frame [2].

While large financial and research institutions publish their insights on market movements in the form of discrete datasets, the feelings and opinions of retail investors are often difficult to assess on a large scale due to their distributed nature. However, research has shown that sentiment analysis (SA) can be used to extract important metrics for retail investors, such as systematic correlation (individuals buy or sell assets in a coordinated manner) [3].

Financial social media have been a phenomenon of the last 15 years and offer an exciting opportunity to apply SA at scale. SA is a method commonly used to assess users' sentiments in social media applications such as Twitter [4] and use them to build machine learning models and classifiers that can later be used to further analyse various financial market datasets.

## Objectives of the project

The first goal is to find social media sentiment datasets suitable for neural network training and ensure that they contain texts that are correctly labelled (as positive or negative sentiment). The resulting text corpora must then be processed to improve the model's results by applying techniques such as word stemming, contraction substitution, and tokenization.

The next major challenge is to design the bidirectional recurrent neural network (BRNN) itself by selecting appropriate hidden layers, placing them in the correct order, and choosing appropriate hyperparameters. The output of this network should be a floating point number indicating that the input corpus belongs to either a positive or negative sentiment class, and a measure of the certainty of the finding (a higher or lower number would indicate higher certainty).

The algorithm should also be able to store the model locally during the training process to ensure that the best scoring model and hyperparameters are preserved.

Finally, I will also compare the performance of this model, as measured by its accuracy, to the existing Native Bayes text classifier from the [NLTK library](https://www.nltk.org/).

## Conclusions

I successfully implemented a bidirectional recurrent neural network specialised to evaluate the sentiments of retail investors with respect to the financial market conditions. The model achieved a satisfactory accuracy of 75% with a relatively high loss of 55%. This means that the model made a relatively small number of large errors, which is makes sense given the discrete nature of the results. The BRNN was able to outperform the prebuilt Naive Bayes text classifier by a significant margin of 11%.

I found that the main limiting factor is the quality of the input data and not the performance of the neural network itself, with a possible exception described below. While there are a large number of datasets dealing with financial sentiment, many contain corpora that are clearly mislabeled or contain other errors, such as off-topic text.

Up to roughly 22nd epoch, the model's loss descreases almost linearly, which is a good indication. However I did notice it starts to increase afterwards. Due to the limited time available, I was not able to determine the root cause of this behaviour and this area could be a good starting point for subsequent research.

## References

[1] Medsker, Larry R., and L. C. Jain. "Recurrent neural networks." Design and Applications 5 (2001): 64-67.

[2] Schuster, Mike, and Kuldip K. Paliwal. "Bidirectional recurrent neural networks." IEEE transactions on Signal Processing 45.11 (1997): 2673-2681.

[3] Kumar, Alok, and Charles MC Lee. "Retail investor sentiment and return comovements." The Journal of Finance 61.5 (2006): 2451-2486.

[4] Sohangir, Sahar, et al. "Big Data: Deep Learning for financial sentiment analysis." Journal of Big Data 5.1 (2018): 1-25.

[5] Socher, Richard, et al. "Recursive deep models for semantic compositionality over a sentiment treebank." Proceedings of the 2013 conference on empirical methods in natural language processing. 2013.

[6] Maas, Andrew, et al. "Learning word vectors for sentiment analysis." Proceedings of the 49th annual meeting of the association for computational linguistics: Human language technologies. 2011.

[7] Yash Chaudhary, 2020, *Stock-Market Sentiment Dataset*, https://www.kaggle.com/dsv/1217821
