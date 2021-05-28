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
QUD is an annotated dataset devoted for anomaly detection in power consumption. Five micro moment classes are defined, in which the first three ones represent normal consumption: “class 0: good usage”, “class 1: turn on”, and “class 2: turn off”. On the other hand, “class 4: excessive power consumption” and “class 5: consumption when outside” describe anomalous consumption.

Those wishing to use the dataset in academic work should cite this paper as the reference. QUD_app-1.csv: this file includes the different kinds of data collected during the measurement campaign: Column 1: Date Column 2: Time Column 3: appID Column 4: occupancy pattern Column 5: Power consumption Column 6: Normalized power Column 7: Quantified power Column 8: Micro-moment class

## Approach towards building classifiers 
Building classifiers I have taken logistic regression and random forest classifiers to compare their performances and evaluating based on different metrics 






