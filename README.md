# Welcome to MBTI-Personality-type-analysis

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on predicting MBTI personality types from people's words expressions from https://www.kaggle.com/datasets/datasnaek/mbti-type.


Contributors:
1) Alistair Yong Jia Jin - Sentiment Analysis
2) Alton Cheah Zhixian - Exploratory Data Analysis
3) Tan Chuan Liang - Rudimentary Word Anlaysis


Problem Definition: 
- Is it possible to accurately predict personality type through people's word choices?
- Which model will be best used to predict it?

Models used:
1) Random Forest Classfier
2) Balanced Random Forest Classifier
3) K Nearest Neighbour Classifier
4) Logistic Regression

Different types of analysis:
1) Rudimentary word frequency analysis: 
- To generate new numerical data derived from the frequency of certain words. Similar to how it was done for EDA, we will find the average number of SPECIFIC words per comment. A reasonable guess at some words that may separate the personalities would be "think", "feel", and "judge" -- the very names of the personality categories. While we include these words in past tense ("thought", "felt", "judged"), it is important to exclude "thinking", "feeling", and "judging" specifically, as the comments are from a personality forum, and these words may be used to refer to the other personality types directly.
2) Sentiment analysis: 
- Using NLTK's sentiment analysis to predict people's MBTI's personality type. This might work as different personality types will have different levels positivity/negativity, so by taking the average sentiment of their past 50 posts, we can try and make use of that as a feature.

Conclusion
- Personality can be predicted by people's expression – Solves our original problem
- Model is overpredicting the "IN" personalities, so instead of predicting all 16 personalities at a go, we predict each dichotomies: I-E, N-S, T-F, J-P 
- In most of the cases, J-P will always have a lower accuracy than the others. A guess would be that J-P is hard to predict for, as there are many context-dependent ways to describe a judged/perceived situation.
- Improve of the problem of overfitting, like how our random forest classifer model, tends to over fit, hence getting that 1.0 accuracy for train set. So we minimize the effect with other models like Logistic Regression and K Nearest Neighbours.

1) For Rudimentary word frequency analysis:
- Balanced Random Forest has the highest accuracy(78.5%) on the data, and thus is the best model for this analysis, as compared to K Nearest Neighbours, Random Forest and Logistic Regression.

2) For Sentiment analysis:
- If we do not balance the data, every dichotomy except T-F is heavily skewed, and if balanced, the accuracy is significantly lower. Therefore conclude that Balanced Random Forest, although overfitted, still has reasonable accuracy(79.1%) on the raw data, and thus is the best model for this analysis, as compared to K Nearest Neighbours, Random Forest and Logistic Regression.



What did we learn from this project?
- Learnt new machine learning models like K Neighbour Classifier, Logistic Regression, Balanced Random Forest Classifier 
- Imbalanced data has a huge impact on the performance of ML models. And so we use SMOTE over-sampler and Tomek cleaning, classes now have equal count to address the root problem of imbalance
- Using NLTK's VADAR Sentiment Analysis to generate new features for sentiment analysis
