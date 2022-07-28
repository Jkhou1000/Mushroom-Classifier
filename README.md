# **Mushroom Classification**

## Identifying Mushrooms 

Over time mushrooms have become an near vital part of our culture, namely in cuisine or biology. One of the most important things about a mushroom is whether or not its poisonous. This project will be an exploartion of the features that mushrooms possess, and the making of a predictive model to classify whether or not they are edible. 

## Data:

The dataset I used comes from the ever reliable UCI Machine Learning Repository, with the aptly named "Mushroom Data Set"
It is a csv of 8214 mushrooms with 22 attributes describing singular and very specific features, Cap color and shape, bruises, odor, and the gill sizes among a myriad of other things. the target value is "Class" which is denoted as "e" or "p", namely "Edible" or "Poisonous"

## Methods, Models, & Results:
There was a distinct lack of NaN or duplicated values, but the data still required some workaround and cleaning. For starters, all of the data is Categorical, Object class. This limits my ability to put out varied data visualizations, and makes exploring correlation or comparing two features together impractical. As such I limited myself to barplots and countplots, as well made a seperate dataframe aggregate by mean to make abstract observations over small percentages of important features. 
Some feature engineering was also done on some of the categories as the values were near identical, and putting them together still made them understandable since they were only differentiated by their locations based on the mushroom's ring (above or below).One of the last changes I made before moving onto modeling was dropping the veil type completely, as while the data dictionary gives me two types of veils, every single mushroom was classified with a 'veil-type' of 'p'(partial) which means my machine model would have no use for it when determining classification. 

After tuning my 3 models, I set up a PCA for them, to help reduce dimensionality and speed it up. Ironically however, this ended up being deleterious to all 3 models.  of the 3 models I went with, Logistic Regression (which was the first I tuned) and KNN ended up having a perfect accuracy, without needing PCA to reduce dimensionality. Random forest slightly trailed behind at 99%. When PCA was applied to Logistic regression, it slightly reduced the score of accuracy and precision. When applied to the other 2, it completely messed them up: Random Forest could only predict everything as edible, and KNN would classify everything as poisonous. I removed PCA from KNN and LR but not Random Forest, as I wanted to show the effect it has on the model's ability to predict properly. ![image](https://user-images.githubusercontent.com/105755535/181650743-151d0c2c-dfb3-4657-a7fa-9956a937427f.png)
