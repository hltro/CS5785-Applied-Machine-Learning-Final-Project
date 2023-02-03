# CS5785-Applied-Machine-Learning-Final-Project

## Motivation
Since the outbreak of COVID-19, we see increasing news stories about the rise of gun-related violence, shoplifting, and hate crimes in New York City. As New Yorkers’ fear of crime grows, our project analyzes crimes reported to the New York City Police Department (NYPD) from 2006 to 2021 (the dataset can be found as “NYPD Complaint Data Historic” on NYC Open Data). We used machine learning models to predict dangerous locations represented by (longitude, latitude) for vulnerable population with certain attributes (e.g., age, race, sex). 

This project can be categorized into application of machine learning algorithms to a novel dataset. It is a meaningful project because analyzing crime data helps us understand the complex factors that contributed to crime events in New York City. Furthermore, this project can be used as a real-world application by sending users alerts once they enter a potentially dangerous location, reminding them to watch their surroundings and avoid potential attacks.  

## Context
Since we are dealing with a large and yearly updating real-world dataset with more than 7.8 million rows and 35 columns of data (as opposed to competing on a machine learning benchmark or doing a theoretical analysis of any aspect of machine learning models), there is not much previous work for us to build upon. We did a search on Kaggle and found several notebooks of people analyzing the same dataset in the past, but their work mostly focuses on data visualization, such as using diagrams to show the top categories of offense or the number of crime events by borough. We did not find any previous work that tries to predict crime hotspots in NYC based on given features of a vulnerable population like we do, so there is no clear benchmark for us to compare the performance of our model with. 
  
In terms of background for our project, we did some exploratory data analysis to understand the general trend of crimes in NYC especially in regard to vulnerable populations and the impact of COVID-19. These are some major conclusions we reached:

Right after the outbreak of COVID and the start of home isolation, there is a significant drop in the number of crimes. This makes sense because when people are constrained at home, there is less opportunity for both potential victims to go out and be subjected to attacks or for potential suspects to go out and commit crimes. In 2021, when home isolation started to ease, we observed a rebound in the number of crimes, although it did not rebound to the same level before COVID.

Analyzing crime data from 2018 to 2021, we found that criminal activity is concentrated in small places or hot-spots that account for half of all crime incidents. Police could focus their resources and attention on these high crime hotspots, thereby more effectively deterring crime incidents and improving the city's safety.

## Method
Based on our input and output data, we decide to perform multi-output regression. This is because - first, we want to output two variables in the end, which leads to multi-output models; second, we hope to predict longitude and latitude, which are continuous numerical values suitable for regression models.  

Specifically, we use three machine learning models (Linear Regression, Random Forest, and Gradient Boosting) to predict potential dangerous locations for certain populations. We will elaborate on definitions of these three models and reasons why we choose them:

Linear Regression: Linear regression models the relationship between two variables by fitting a linear equation to observed data. We choose Linear Regression as our baseline model, since it is relatively simple in the underlying logic and more interpretable than other advanced models. Also, Linear Regression allows us to gain a basic understanding of the relationships between dependent variables (in our case, locations that are potentially dangerous to certain populations) and independent variables (population’s attributes, such as age, race, and sex). 

Random Forest: Random Forest grows and combines multiple decision trees to create a “forest”. The “forest” is a bagged decision tree model that splits on a subset of features on each split. We choose Random Forest for our regression problem because it is robust to outliers, has low bias, and is able to handle unbalanced data. By using Random Forest, we hope to understand more that features (victims’ age, race, and sex) have with the target (longitude, latitude) and the degree of influence they have. 

Gradient Boosting: Gradient Boosting relies on the intuition that the best possible next model, when combined with previous models, is able to minimize the overall prediction error. We decide to use Gradient Boosting so as to minimize bias error of the model. Furthermore, since our dataset is large, we hope that Gradient Boosting helps us get accurate predictions with high prediction speed. 
