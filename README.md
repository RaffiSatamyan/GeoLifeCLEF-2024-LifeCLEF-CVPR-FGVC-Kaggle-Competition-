# GeoLifeCLEF-2024-LifeCLEF-CVPR-FGVC-Kaggle-Competition-
# Overview
This challenge aims to predict plant species in a given location and time using various possible predictors: satellite images and time series, climatic time series, and other rasterized environmental data: land cover, human footprint, bioclimatic, and soil variables.
# Competition Description
Predicting plant species composition and its change in space and time at a fine resolution is useful for many scenarios related to biodiversity management and conservation, improving species identification and inventory tools, and educational purposes.

This challenge aims to predict plant species in a given location and time using various possible predictors: satellite images and time series, climatic time series, and other rasterized environmental data: land cover, human footprint, bioclimatic, and soil variables.

To do so, we provide a large-scale training set of about 5M plant occurrences in Europe (single-label, presence-only data) as well as a validation set of about 5K plots and a test set with 20K plots, with all the present species (multi-label, presence-absence data).

The difficulties of the challenge include multi-label learning from single positive labels, strong class imbalance, multi-modal learning, and large-scale.
![image](https://github.com/RaffiSatamyan/GeoLifeCLEF-2024-LifeCLEF-CVPR-FGVC-Kaggle-Competition-/assets/73477594/34e7f8ea-b8e7-476b-9294-4b963b4ba563)
# Motivation

Predicting the plant species present at a given location is helpful for many biodiversity management and conservation scenarios.

First, it allows for building high-resolution maps of species composition and related biodiversity indicators such as species diversity, endangered species, and invasive species. In scientific ecology, the problem is known as Species Distribution Modelling.

Moreover, it could significantly improve the accuracy of species identification tools - such as Pl@ntNet - by reducing the list of candidate species observable at a given site.

More generally, it could facilitate biodiversity inventories by developing location-based recommendation services (e.g., on mobile phones), encouraging citizen scientist observers' involvement, and accelerating the annotation and validation of species observations to produce large, high-quality data sets.

Finally, this could be used for educational purposes through biodiversity exploration applications with features such as quests or contextualized educational pathways.

# Evaluation

The evaluation metric for this competition is the samples-averaged F1
-score (called F-Score Beta (Micro) on Kaggle) computed on the test set made of species presence-absence (PA) samples. In terms of machine learning, it is a multi-label classification task. The F1
-score is an average measure of overlap between the predicted and actual set of species present at a given location and time.
Each test PA sample i
 is associated with a set of ground-truth labels Yi
, namely the set of plant species (=speciesId) associated with a given combination of the columns patchID and dayOfYear (see the Data tab for details on the species observation data structure).
For each sample, the submission will provide a list of labels, i.e. the set of species predicted present Yˆi,1,Yˆi,2,…,Yˆi,Ri
.
The micro F1
-score is then computed using

F1=1N∑i=1NTPiTPi+(FPi+FNi)/2Where⎧⎩⎨⎪⎪⎪⎪TPi= Number of predicted species truly present, i.e. |Yˆi∩Yi|FPi= Number of species predicted but absent, i.e. |Yˆi∖Yi|FNi= Number of species not predicted but present, i.e. |Yi∖Yˆi|


