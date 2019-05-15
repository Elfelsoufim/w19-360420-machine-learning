# Error Analysis
## 360-420-DW - Section 02
## Elfelsoufi Mohamed Amine

### Distributions of Model Accuracy
Every time we run the model, the datapoints that are taken from the whole data point list (to make the test set and the training set) are random. Furthermore,these data points are shuffled and placed randomly. This does that the neighbors with which we compare the test datapoint (that we are trying to predict its label) are always different. The smaller the number of neighbors at which we look, the more there is chance that we will look at a homogenous set of points, which can falsifie the prediction (ie. the closest neighbor can be in fact very far compared to the other datapoint that are not neighbors and that we don't look at).



The very sensitive baseline that is crucial for our model's accuracy is the data set itself. For this model specifically, it is important that all the possible target labels be present in equal numbers. This is because the data points are selected randomly for the train and test set, and that they are shuffled and placed randomly also. Thus, if a label is present in a greater number, this falsifies the result (the prediction). A label (or target) present in greater number in the dataset will be present in a greater number in the test set (because of the laws of probability) and will be present more frequently in the neighborhood at which we look. Therefore, there is a greater possibility that this more frequent label will be more often the closest neighbor and that the result predictions will be more often this same label not because it is true but because it was more frequent. 


### Analysis of different error types

A False Negative is a specimen that our model predicted to be an irrelevant element and didn't select it, ie. For a program that diagnose sick people, healthy people are irrelevant specimens. A false negative is predicted as irrelevant while it actually is relevant (that would mean that it was sick but didn't get diagnosed as sick) and should have been selected.

A False Positive is a specimen that was predicted to be relevant (i.e sick) while in fact he is irrelevant (not sick). 

These two categories are directly linked to accuracy. The larger the number of specimens in this two categories, the less accurate the model is.



Precision and recall are two different kinds of accuracy.

Precision is the accuracy of the model to predict and select relevant models. The higher the precision, the more chance that the selected specimens are genuinly relevant (i.e a higher chance that the patients diagnosed with sickness are truly sick).

Recall is the accuracy of the model to predict and select all the relevant models. The higher the recall, the better the model is at spotting/detecting a relevant specimen and selecting it. (i.e it is better at diagnosis and spotting when someone is sick).

Precision means the certainty that the selected specimens are relevant. Recall means the ability to detect and select all the relevant specimen in the dataset. Precision can be increase by selecting less specimens (less chance to make a mistake). Recall is much more relevant in term of accuracy (cannot be influenced by the size of the dataset/population).

#### K parameter
The k parameter means the number of neighbors we look at to make the prediction. A bigger k yields more precision, because there is more chance that the closest neighbor is present in the "neighborhood" that we look at. Smaller k yields the opposite result.
Similarly, a higher k yields a better recall. The specimens have a higher chance to be put in the right category (or prediction or label) because there is a higher chance the neighbor with the right label (closest) will be present in the sample neighborhood that we look at for our predictions.