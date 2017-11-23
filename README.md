# Practical Machine learning peer assignment project
Tak Au  
`r format(Sys.Date(), "%B %d, %Y")`  



### Introduction 
  
In this project, the goal is to use data from accelerometers on the belt, forearm, arm, and dumbell of 6 participants, using the "classe" variable in the training set as outcome and any of the other variables to quantify the performance of each exercise. The report should describe how the model is built, how cross validation is used, the expected out of sample error and how the choices are made.   
   


### Background  
  
Using devices such as Jawbone Up, Nike FuelBand, and Fitbit it is now possible to collect a large amount of data about personal activity relatively inexpensively. These type of devices are part of the quantified self movement - a group of enthusiasts who take measurements about themselves regularly to improve their health, to find patterns in their behavior, or because they are tech geeks. One thing that people regularly do is quantify how much of a particular activity they do, but they rarely quantify how well they do it. In this project, the goal will be to use data from accelerometers on the belt, forearm, arm, and dumbell of 6 participants. They were asked to perform barbell lifts correctly and incorrectly in 5 different ways. More information is available from the [website here]( http://web.archive.org/web/20161224072740/http:/groupware.les.inf.puc-rio.br/har) (see the section on the Weight Lifting Exercise Dataset).   
  
  
#### Data  
  
[The training data for this project are available here](
https://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv)

[The test data are available here](
https://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv)  
  
  
### Method  
  
In this project I used the random forest in the caret package to construct the train model and the k-fold cross-validation was used.  
  
The key advantages of the caret package is its ability to estimate an out of sample error by aggregating the accuracy analysis across a series of training runs. This is because caret automates the process of fitting multiple versions of a given model by varying its parameters and/or folds within a resampling / cross-validation process.  
One trade off that we made in this analysis was changing the resampling method from the default of bootstrapping to k-fold cross-validation. The change in resampling technique may trade processing performance for reduced model accuracy. However, our analysis shows that the 5 fold cross-validation resampling technique delivered the same accuracy as the more computationally expensive bootstrapping technique.

For the purposes of this analysis, we chose only to vary the resampling method for train(x,y,method="rf",...), leaving other parameters such as mtry constant.   
  
### Acknowledgement  
  
The data for this project come from [http://web.archive.org]( http://web.archive.org/web/20161224072740/http:/groupware.les.inf.puc-rio.br/har). They have been very generous in allowing their data to be used for this kind of assignment.  

