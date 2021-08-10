# Unsupervised Data Augmentation Experimentations
## Final Project for NLP W266 class

UC Berkeley MIDS Program 

Joanna Yu, Spring 2020

### Introduction
While there has been rapid development in the field of Natural Language Processing in the last decade, the scarcity of labeled data remains a problem. Research has shown that unlabeled data can improve adversarial robustness and consistency training is among those that show great promises. The recent work done by Google, titled “Unsupervised Data Augmentation for Consistency Training”, shows that back-translation, as an advanced data augmentation technique, is an effective way to improve model performance. This work focuses on expanding the framework from the paper to further investigate the tradeoff between labeled and unlabeled data and the role of domain relevance in semi-supervised learning using unsupervised data augmentation.

### Objective 

1. Track model performance with respect to the proportion of labeled vs unlabeled data.

2. Investigate how domain relevance of unlabeled data affects performance of the semi-supervised model.

### About the Data

The main dataset, IMDb movie review dataset, is an ideal dataset for the proposed experiments since it contains a good amount of labeled and unlabeled examples. In addition, using a movie review dataset allows for the possibility of appending additional movie review data if one wishes to experiment with data beyond the size of the IMDb.


 **Data Type** | **Postive** | **Negative** | **Total**
 --- | --- | --- | --- 
Labeled Training Data | 12,500 | 12,500 | 25,000
Test Data | - | - | 25,000
Unlabeled Training Data | - | - | 50,000

Dataset for domain relavance experimentations:

**Dataset** | **Domain Relevance**
 --- | --- 
IMDb Movie Reviews | In-Domain
Amazon Movie and TV Reviews | In-Domain
Amazon Office Product Reviews | Semi-In-Domain
Twitter Airline Sentiment | Semi-In-Domain
Kaggle Natural Disaster Tweets | Out-of-Domain

### Experiments
#### Environment

* A series of notebooks and scripts are run on Google Colaboratory Pro using GPU/TPU environment. 
* A large amount of Google Cloud Storage is used for this project due to the size of BERT and model checkpoint files. 
* Depending on the total size of data being fine-tuned and trained, a single model takes 30 minutes to 6+ hours to run on a TPU.

#### Metric - Error Rate

#### Exploration of the Tradeoff between Labeled and Augmented Unlabeled Data

* 7 different amounts of labeled data are selected. 
* Model performances are tracked for every increase of 4,000 augmented unlabeled examples from 0 to 16,000, at which point the error rate begins to level off so additional models are run at 24,000, 48,000, and the full dataset of 69,972 examples.

#### Exploration of the Effect of Domain Relevance
* Unlabeled data is kept constant at 16,000 examples so the results are comparable across all datasets.
* When feasible, only examples over 128 tokens are selected so training can be done on longer text.
* Back-translation is performed to augment the unlabeled data.

### Results
#### Relationship between Labeled and Unlabeled Data
![UDA Comparison](/images/imdb_UDA_comparison.png)


The `UDA main` notebook contains the experimentation done in this project. The `results` notebook contains the results and graphs.

#### Acknowledgement
The experiments done in this project is leveraged from the framework developed by the UDA paper, https://arxiv.org/pdf/1904.12848.pdf
