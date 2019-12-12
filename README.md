# Robot_or_not
Code for ML lab final project
## Description 
This data is from the Kaggle Competition  [Facebook Recruiting IV: Human or Robot?](https://www.kaggle.com/c/facebook-recruiting-iv-human-or-bot/data). The data is from an online aution platform (not Facebook), and is tabular data of web server logs. bids.csv is the main data file, with 7.3 million rows, with columns like bidder_id, ip, country, etc. There are 2,013 unqiue users in this dataset.

## Goal 
We want to find the model that best classifies a user based on their online behavior as a bot, or human bidder. This is important because correctly identifying robots provides better customer experience for humans.

## Process
Our data is heavily imbalanced, with 94.9% humans and 5.1% robots. To account for this imbalance with used the SMOTE method. We feature engineered and identified features that helped distinguish between humans and robots, based on the mean of their distributions. We created an Sklearn pipeline to impute values, and test out the performance of different models. 

For our metric we evaluted the models using weighted F1 score, but we also looked at AUC ROC. 

After determining the best model, we perfomed a Random search for hyperparameters.

## Summary

Our best performing model was the Random Forest Classifier, with our final weighted F1 score as ~0.95 on the validation set. 

One significant aspect about our data was that is was not robust; i.e. there were many codependent features. This was found empirically using the Random Forest feature importance. To alleviate this effect, we performed PCA to decorrelate our features. This did not significantly imporve our model performace, however, it could be a useful technique for future exploration. 
