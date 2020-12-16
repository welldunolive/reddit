# Reddit Classification

Jeong Dam (James) Lee

### Contents:
- [Goal](#Goal)
- [Summary](#Summary)
- [Models/Conclusion](#Models/Conclusion)
- [Thoughts](#Thoughts)

## Goal

We want to classify two different subreddits (r/DunderMifflin and r/PandR) only using the comments. Using Natural Language Processing (NLP) and different classification models, I wanted to see if there are clear differences between the two subreddits.

The subreddits are chosen solely from my own interest. These two shows, the Office and Parks and Recreation, share some writers as well as directors.

## Summary

Data needed for this project were collected through Pushshift API. Some data cleaning was required to remove punctuations, html, hyperlinks and special characters. I have collected 10,000 comments from both of the subreddits. .csv file for submission on the Office is also available.

Some argue that one show is better than the other but I want to focus more on the context of the comments to classify the shows. Below are the models that I have used to score them.

- Logistic Regression
- Random Forest Classifier
- Naive-Bayes Classifier

My models were heavily focused on CountVectorizer. Models are scored from just pipeline and GridSearchCV for all of the models.

Below shows my target (getting the subreddit correct) and body

| Field     | Type   | Description |
|-----------|--------|---------|
| cleaned | object | comments |
| subreddit     | int    | 1 = r/PandR, 0 = r/DunderMifflin |

### Models/Conclusion

| Model               | Training Score | Test Score |Accuracy |
|---------------------|----------------|------------|----|
| Logistic Regression | 0.98          | 0.69     |.69 |
| Random Forest         | 0.99          | 0.68     |.69 |
| Naive-Bayes      | 0.78            | 0.70      |.70 |

Looking at the train/test score, the least overfit model was Naive-Bayes, which explains the accuracy. I was not fully satisfied with the scores and accuracy but thinking realistically, getting the right subreddit 7/10 times is not too bad.
The model uses words only; the model could have improved if I separated into spacey instead.

### Thoughts
I would have liked to collect more data and clean the comments in a different way with different stopwords. Each gridsearch took about 20-30 mins to fit. In addition, checking different classifiers such as KNN and SVM could have shown better results.

As mentioned above, these are models only using the comments. Exploring different features, such as length of the comments or the title of the posts, can help and increase accuracy scores.
