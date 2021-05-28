# Anomalous-Energy-Consumption
A novel approach to detect anomalous energy consumption using micro-moments as context for classification of anomalies. 

## Introduction 
Enormous amounts of data are being produced everyday by sub-meters and smart sensors installed in residential buildings. 
If leveraged properly, that data could assist end-users, energy producers
and utility companies in detecting anomalous power consumption and understanding the causes of
each anomaly. Therefore, anomaly detection could stop a minor problem becoming overwhelming.
Moreover, it will aid in better decision-making to reduce wasted energy and promote sustainable
and energy efficiency behavior. 

The whole concept of finding anomalous energy consumption has it's limitations due to absence of (i) precise definitions of anomalous
power consumption, (ii) annotated datasets, (iii) unified metrics to assess the performance of existing
solutions. Which led the researchers at Qatar University Energy Lab, namely, Qatar University dataset (dataset that I used for current project) to conduct 
measurement campaign for resdential building with annotated anomalies. 

## Definition of anomalous energy consumption 
Energy usage is very dynamic in nature which means that consumer uses energy as per their needs & that creates moments of transients like switching ON/OFF
or using appliance without them being in room. This type of behaviour causes moments which is called as *"micro moments"*. The QUD (Qatar University dataset) had
already extracted these micro moments as different classes. The whole process of labelling these classes from **un-annoated data** is mentioned with the paper on which 
my research is based on is within this repo. 

![image](https://user-images.githubusercontent.com/83111155/119937160-ebb6c700-bfa7-11eb-8547-4c3430958717.png)

*Flowchart of a supervised anomaly detection scheme based on DNN used to detect two different abnormalites, i.e. excessive consumption and consumption while outside.*

## Description of Dataset 
QUD is an annotated dataset devoted for anomaly detection in power consumption. Five micro moment classes are defined, in which the first three ones represent normal consumption: “class 0: good usage”, “class 1: turn on”, and “class 2: turn off”. On the other hand, “class 3: excessive power consumption” and “class 4: consumption when outside” describe anomalous consumption.

Those wishing to use the dataset in academic work should cite this paper as the reference. QUD_app-1.csv: this file includes the different kinds of data collected during the measurement campaign: Column 1: Date Column 2: Time Column 3: appID Column 4: occupancy pattern Column 5: Power consumption Column 6: Normalized power Column 7: Quantified power Column 8: Micro-moment class

## Approach towards building classifiers 
Building classifiers I have taken logistic regression and random forest classifiers to compare their performances and evaluating based on different metrics.

![distribution of classes](https://user-images.githubusercontent.com/83111155/119988646-f2fbc600-bfe3-11eb-817f-57ef16b188e9.png)

*Distribution of classes as percentage of occurance*

as per distribution of classes it is clear that occurance of **Class 4** is higher than that of **Class 3** which means this building energy consumption is not excessive but there is lot of cases of energy consumption when there is "no-occupant" in the room.   

![image](https://user-images.githubusercontent.com/83111155/119988164-74068d80-bfe3-11eb-8f4c-2b140412ea55.png)

*Indentification of Anomalous region by visualizing the micro-moments*
 
 as per above visualization, shows the exact boundaries of decision to take in classifying the multi-class hence, Logistic regression is best for this type of classification and also random forest classifier is also used to see the outcome of both of the classifiers. 
 
 ## Evaluation metrics of both of the classifiers
 
 Models | Accuracy Score |Macro Precision | Macro Recall| Macro F1 score
------------ | ------------- | ------------- | ------------- | -------------                          
Logistic Regression| 0.86 |0.54|0.40|0.37
Random Forest Classifer |0.96 |0.69|0.80|0.73

## Insights 
- From the distribution of classes that is clear that due to human behaviour there exists anomalous power consumption hence, an positive reinforcement is to be encourged among the tenets of the building in saving energy. 
- Random Forest classifier has performed very well with this dataset. 
- Futher in production this model has to train against consumer's feedback as well because the rate of false negatives can led to false alarms thus, somehow integration of consumer's feedback through some program to check on them for comfort makes sense to use this model. 

