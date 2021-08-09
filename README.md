# Unsupervised Data Augmentation Experimentations
## Final Project for NLP W266 class

UC Berkeley MIDS Program 

Joanna Yu, Spring 2020

### Introduction
While there has been rapid development in the field of Natural Language Processing in the last decade, the scarcity of labeled data remains a problem and researchers are looking for better ways to make use of the abundant unlabeled data for semisupervised
learning. Research has shown that unlabeled data can improve adversarial robustness and consistency training is among those that show great promises. The recent work done by Google, titled “Unsupervised Data Augmentation for Consistency Training”, shows that back-translation, as an advanced data augmentation technique, is an effective way to improve model performance. This work focuses on expanding the framework from the paper to further investigate the tradeoff between labeled and unlabeled data and the role of domain relevance in semi-supervised learning using unsupervised data augmentation.

### Objective 

1. Track model performance with respect to the proportion of labeled vs unlabeled data.

2. Investigate how domain relevance of unlabeled data affects performance of the semi-supervised model.

### About the Data

The main dataset, IMDb movie review dataset, is an ideal dataset for the proposed experiments since it contains a good amount of labeled and unlabeled examples. In addition, using a movie review dataset allows for the possibility of appending additional movie review data if one wishes to experiment with data beyond the size of the IMDb.


 - | **Postive** | **Negative** | **Total**
 ___ | ___ | ___ | ___ 
**Labeled Training Data** | 12,500 | 12,500 | 25,000
**Test Data** | - | - | 25,000
**Unlabeled Training Data** | - | - | 50,000

Dataset for domain relavance experimentations:

_ | _
_ | **Domain Relevance**
**IMDb Movie Reviews** | In-Domain
**Amazon Movie and TV Reviews** | In-Domain
**Amazon Office Product Reviews** | Semi-In-Domain
**Twitter Airline Sentiment** | Semi-In-Domain
**Kaggle Natural Disaster Tweets** | Out-of-Domain




### Results
The `UDA main` notebook contains the experimentation done in this project. The `results` notebook contains the results and graphs.

#### Acknowledgement
The experiments done in this project is leveraged from the framework developed by the UDA paper, https://arxiv.org/pdf/1904.12848.pdf
