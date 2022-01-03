Predicting the survival in Titanic is the entry-level machine learning project in Kaggle. It is easy but getting a high rank on the leaderboard is challenging. After tuning hyperparameters, using different datasets and machine learning algorithms (KNN, Random Forest Classifier, Bayes Classifier, and Many deep learning models), and some tricks, my rank finally becomes 811 out of 13921 teams with a score of 0.79665. I record several noticeable things from predicting the survival in this article. 

Change of positions of neurons in the input layer may lead to a different conclusion at first glance. Two things happened when the neuron receiving the Age value was moved to the end. 1) Performance plummeted (from 0.77 to 0.72); 2) The performance based on the training set with missing ages predicted by another deep learning model > the counterpart with NA ages replaced by the mode of ages > the one with datasets deleting all the missing ages. However, this likely result did not appear before changing the neuron's position.

Fully-Connected DL Model performed better than the Deep and Wide Model, Deep Cross Network Model, Residual Network Model, and Dense Network Model. When I used Deep Cross Network to train a recommendation system on a large amount of Wechat data (Titanic only contains 891 records), the Cross Network generated usefully expert features, which outperformed tree-based algorithms with hundreds of hand-selected features. But this did not work in Titanic.

The features generated from the deep learning model did not improve the performance of Random Forest Classifier and KNN. After adding two hidden layers in the DL Model, I saw that the performance improved, so I fed those generated features to RFC and KNN. But their performance dropped.

When ensembling 22 models, learnable weights were beaten by a hand-chosen weight for the Random Forest Classifier. In the beginning, the weights for all models were 1; then the performance can be improved by learning those weights; but when I improved the weight of RFC to 2 by hand (other weights all around 1), the performance was significantly improved again.


