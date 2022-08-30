# Final_Bootcamp_Project_Segment2

## Communication protocols
I will work on this project on my own because I wasn´t sure I was going to be able to finish the course. I had delays on my Challenge deliverables and had to work on those first. I didn´t want to delay anyone else with their own projects so I decided to work on my own.

## Project outlined
To check the drafted project around the following topics, please refer to the [draft presentation for Segment 2](https://docs.google.com/presentation/d/1vevdRSbZUXFwZ-tOMe8PvFz4bRxzGSoixrDqNfBRb_c/edit#slide=id.p). You will find information about things like: Selected topic, Reasons for the selected topic, Questions that want to be answered ,and the start of all the Analysis Phase.

As outlined in the presentation, the models that will be used are:
* **Kmeans clustering** to get to the personas will be directing the communication towards
* **Random forest** to be able to know what variables impact more in the generated personas and be able to predict the persona that best fits for future clients. For this, I attached the [documentation]([https://github.com/karen-trena/Final_Bootcamp_Project/blob/main/random%20forests.ipynb](https://github.com/karen-trena/Final_Bootcamp_Project_Segment1.git)) on the first segment deliverable.

## Preliminary data preprocessing
For this stage, I had to first take a look at the data. There I could see that I had 18 variables and 8950 observations. After taking a look at the head of the dataset I could see that 1 variable was an identifier and the rest were numeric variables. Anyhow, I checked how the variables were classified and saw that the identifier was saved as an "object". The rest of the variables except 3 were saved as "float" and the other 3 were saved as "integers". For visual representation of this please check [slide 8](https://docs.google.com/presentation/d/1vevdRSbZUXFwZ-tOMe8PvFz4bRxzGSoixrDqNfBRb_c/edit#slide=id.g1489f308939_0_248).

From there I made a descriptive statistics analysis and found there were variables with missing data and many outliers. To deal with the missing data I decided to input the mean of the dataset in those cells where we had missing data. This was with the intention of not losing the whole rows as it would have been a loss of 314 lines. For more information around this, please check [slide 9](https://docs.google.com/presentation/d/1vevdRSbZUXFwZ-tOMe8PvFz4bRxzGSoixrDqNfBRb_c/edit#slide=id.g148a0b4136c_0_17).

To manage the outliers, I decided to try 2 things:
* First I tried making intervals considering the variability within each variable. Therefore the intervals generated would be completely different among each variable. Even though I though this was going to be the best approach, I realized that the inertia was better for the Kmeans classification with the model explained in the next bullet. In total I used 17 interval combinations.
* The second thing I tried was making intervales considering the same for as much variables as I could possibly use. There were variable that went from 50 to 120,000 or variables that went from 0 to 500,000 as an example. For these type of variables I used the same intervals, but for data that displayed probabilities, I chose other intervals. In total I used 3 interval combinations to fit all possible variables.This model gave me the best inertia for the Kmeans model using 4 clusters.

For more information around this please consult [slide 10](https://docs.google.com/presentation/d/1vevdRSbZUXFwZ-tOMe8PvFz4bRxzGSoixrDqNfBRb_c/edit#slide=id.g148a0b4136c_0_27).
The notebook used is this [one](https://github.com/karen-trena/Final_Bootcamp_Project_Segment2/blob/main/Intento6ProyectoBuenisimo%20%20(18%20variables%20y%204%20clusters)%20rangos%20iguales.ipynb). Please refer to lines 8 to 10 and the description above those lines.

## Preliminary feature selection
With all these exploratory and cleaning phase I was able to proceed with Kmeans to have a variable I would wish to predict for future observations. 

With the clusters generated, I wanted to create Personas or personalities that could be easy to identify in the society and to whom I could direct different types of communication campaigns according to their own needs and consumption habits. Let´s remember that the data we had was information about how much people consume from their credit lines, if they use cash, if they buy a lot, if they use installments, etc. With the process done in this phase I was able to generate 4 Personas. Please consult [slides 11 to 13](https://docs.google.com/presentation/d/1vevdRSbZUXFwZ-tOMe8PvFz4bRxzGSoixrDqNfBRb_c/edit#slide=id.g148a0b4136c_0_0). to check the profiles of the Personas generated. I tried several models according to the interval combinations from the previous section and different number of clusters, and while analysing the profiles generated, using 4 clusters was the model that made more sense to me for the purpose of this project. Once I finish this stage, I will start working on the predictive model.

## Description on the training and test datasets
 I haven´t got to this stage, but I will use the predefined training and test proportion of datasets that Python works with. The default for Python is 25% for test dataset and 75% for training dataset, please consult [here](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html) for further information. This is implemented by default using the scikit-learn library from Python on the model_selection package, specifically on the function train_test_split(), but if I would like, I could change it any other proportion of my preference. From this [source](https://www.researchgate.net/post/Is-there-an-ideal-ratio-between-a-training-set-and-validation-set-Which-trade-off-would-you-suggest), I found that anything in between 60% and 90% for the training set is considered adequate so I decided to work with the default proportion. It´s important to be too creative on going out of the recommended intervals as this could lead to underfitting or overfitting the model.

## Explanation of the models choice, benefits, and limitations
The models I chose are:
* KMeans Clustering:
  I chose this model because I want to be able to feel more confident using cluster analysis to generate personas and create segmentation that doesn´t necessarrily depend on one variable we count with on my jobs datasets. Instead we might need to create new variables to understand better the people we serve.
* Random Forests:
  I think this is a very interesting model not so used in my company for now and I think it is super useful as it can work with many type of data and give importances to each variable according to how much they contribute. I would be awesome to count with a visual aid to know how each variable interacts with other ones... but for that we might need to consider a decision tree instead afterwards.
  
For more information on why I selected these models, please consult [slides 3](https://docs.google.com/presentation/d/1vevdRSbZUXFwZ-tOMe8PvFz4bRxzGSoixrDqNfBRb_c/edit#slide=id.g1489f308939_0_183).
For more information about the models, please consult [slide 7](https://docs.google.com/presentation/d/1vevdRSbZUXFwZ-tOMe8PvFz4bRxzGSoixrDqNfBRb_c/edit#slide=id.g148a0b4136c_0_53).

## Databases
* This is the [original dataset](https://github.com/karen-trena/Final_Bootcamp_Project_Segment2/blob/main/CCGENERAL.csv)
* This [dataset](https://github.com/karen-trena/Final_Bootcamp_Project_Segment2/blob/main/OUTPUT_WITH_4_PERSONAS_AND_CATEGORIES.csv) contains the clusters and the intervals generated for each variable.
* This [dataset](https://github.com/karen-trena/Final_Bootcamp_Project_Segment2/blob/main/OUTPUT_WITH_4_PERSONAS.csv) contains the original dataset with the clusters included. This were joined in Pandas and it would be useful if these were the only pieces of information. Nonetheless, as there could be much more data on the Company to join with this one, we decided to leave the original dataset, bullet 1 dataset, and the dataset with the clusters and intervals created, bullet 2 dataset, separately in PG Admin. This is the 
! [ERD with relationships] ()

The proof of the existing datasets in PG Admin is shown in the following screenshots:
* [OriginalDataset](https://github.com/karen-trena/Final_Bootcamp_Project_Segment2/blob/main/Picture1.png)
* [DatasetWithIntervalsAndClusters](https://github.com/karen-trena/Final_Bootcamp_Project_Segment2/blob/main/Picture2.png)


## Dashboard
I will use Tableau to create the dashboard. I will try to make the cluster Persona elegible for the analyst and once selecting the persona, the data from the different variables will be displayed so they know their consumption habits to be able to create the correct email campaigns for them.

This is the storyboard.
! [Storyboard]()

