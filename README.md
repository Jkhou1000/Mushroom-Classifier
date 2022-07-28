# **Mushroom Classification**

## Identifying Mushrooms 

Over time mushrooms have become an near vital part of our culture, namely in cuisine or biology. One of the most important things about a mushroom is whether or not its poisonous. This project will be an exploartion of the features that mushrooms possess, and the making of a predictive model to classify whether or not they are edible. 

## Data:

The dataset I used comes from the ever reliable UCI Machine Learning Repository, with the aptly named "Mushroom Data Set"
It is a csv of 8214 mushrooms with 22 attributes describing singular and very specific features, Cap color and shape, bruises, odor, and the gill sizes among a myriad of other things. the target value is "Class" which is denoted as "e" or "p", namely "Edible" or "Poisonous"

## Methods, Models, & Results:
There was a distinct lack of NaN or duplicated values, but the data still required some workaround and cleaning. For starters, all of the data is Categorical, Object class. This limits my ability to put out varied data visualizations, and makes exploring correlation or comparing two features together impractical. As such I limited myself to barplots and countplots, as well made a seperate dataframe aggregate by mean to make abstract observations over small percentages of important features. 

Some feature engineering was also done on some of the categories as the values were near identical, and putting them together still made them understandable since they were only differentiated by their locations based on the mushroom's ring (above or below).One of the last changes I made before moving onto modeling was dropping the veil type completely, as while the data dictionary gives me two types of veils, every single mushroom was classified with a 'veil-type' of 'p'(partial) which means my machine model would have no use for it when determining classification. 

After tuning my 3 models, I set up a PCA for them, to help reduce dimensionality and speed it up. Ironically however, this ended up being deleterious to all 3 models. Out of the 3 models I went with, Logistic Regression and KNN ended up having a perfect accuracy without needing PCA to reduce dimensionality. Random forest slightly trailed behind at 99%. When PCA was applied to Logistic regression, it slightly reduced the score of accuracy and precision. When applied to the other 2, it completely messed them up: Random Forest could only predict everything as edible, and KNN would classify everything as poisonous. I removed PCA from KNN and LR but not Random Forest, as I wanted to show the effect it has on the model's ability to predict properly. ![image](https://user-images.githubusercontent.com/105755535/181650743-151d0c2c-dfb3-4657-a7fa-9956a937427f.png)

Finally as a last touch, I grabbed the coeffecient values from the LogReg model and converted them to absolute values and assigned them to the corresponding feature names they represented, then sorted them by descending value. This isolated the most important values used by the Logreg model in order to correctly predict everything (Namely the odor and spore print colors were the most important and featured in 9 of the top 10 values)


####  Countplots
![image](https://user-images.githubusercontent.com/105755535/181651453-5aff286a-c13a-4463-a3eb-754f020e8f6d.png)
The above plots were used to explore multiple values with classification as the hue in order to visualize and analyze important features and if they could help classify if a mushroom is edible or not. This plot also helped me realize that I could concactenate certain features, namely the features revolving around the stalk.

#### Aggregated mean values
![image](https://user-images.githubusercontent.com/105755535/181651852-7e6b68cc-6c2d-4207-a6cf-9de5f2c50e4c.png)
These barplots are isolations of an aggregated dataframe after One Hot Encoding. The example I've given shows that the mushrooms that have features that can exclusively identify if a mushroom is edible make up a very small percentage of this dataset 

## Recommendations

Both KNN and Logistic Regression serve their purpose and are 100% accurate but of the two I would still use Logistic Regression. Its default parameters will give perfect predictions on this model, while KNN may run slower with used with larger datasets even after its tuned. Logistic Regression also just works better since this is a binary classification problem. The model should be ideally used for classifying whether or not a mushroom is edible or not based on multiple features it may possess.

## Limitations and Next Steps
The logreg model's incapable of multivariate classification, and it might only do well with a high number of attributes and values. Its best features also had to do with very specific features such as odor and spore print color, which means it might not be as effective without features similar to that which allows the model's perfect accuracy. Further iterations may require different types of datasets and tuning.

## Contact
Any questions or comments can be directed to joshguy62@gmail.com
