# **Mushroom Classification**

## Identifying Mushrooms 

Over time mushrooms have become an near vital part of our culture, namely in cuisine or biology. One of the most important things about a mushroom is whether or not its poisonous. This project will be an exploartion of the features that mushrooms possess, and the making of a predictive model to classify whether or not they are edible. 

## Data:

The dataset I used comes from the ever reliable UCI Machine Learning Repository, with the aptly named "Mushroom Data Set"
It is a csv of 8214 mushrooms with 22 attributes describing singular and very specific features, Cap color and shape, bruises, odor, and the gill sizes among a myriad of other things. the target value is "Class" which is denoted as "e" or "p", namely "Edible" or "Poisonous"

## Methods:
There was a distinct lack of NaN or duplicated values, but the data still required some workaround and cleaning. For starters, all of the data is Categorical, Object class. This limits my ability to put out varied data visualizations, and makes exploring correlation or comparing two features together impractical. As such I limited myself to barplots and countplots, as well made a seperate dataframe aggregate by mean to make abstract observations over small percentages of important features.
Some feature engineering was also done on some of the categories as the values were near identical, and putting them together still made them understandable since they were only differentiated by their locations based on the mushroom's ring (above or below) I also dropped the veil type completely, as while the data dictionary gives me two types of veils, every single mushroom was classified with a 'veil-type' of 'p'(partial) which means my machine model would have no use for it when determining classification
