# Agrifield-Challenge

![planted-field-sunlit-22013723](https://user-images.githubusercontent.com/98299478/225262287-19b690b2-04ee-4979-86b0-8d6f28e3620d.jpg)


Small farms (<2ha) produce about 35% of the world’s food, and are mostly found in low- and middle-income countries. Reliable information about these farms is limited, making support and policy-making difficult. Earth Observation data from satellites such as Sentinel-2, in combination with machine learning, can help improve agricultural monitoring, crop mapping, and disaster risk management for these small farms.

In this challenge, the goal is to classify crop types in agricultural fields across Northern India using multispectral observations from Sentinel-2 satellite. Fields are located in various districts in states of Uttar Pradesh, Rajasthan, Odisha and Bihar. The AgriFieldNet India training dataset is generated by the Radiant Earth Foundation, using the ground reference data collected and provided by IDinsight's Data on Demand team.

The dataset for this competition includes satellite imagery from Sentinel-2 cloud free composites (single snapshot) and labels for crop type that were collected by ground survey. The labels are derived from the survey conducted by IDinsight. The Sentinel-2 data are then matched with corresponding labels.

The dataset contains 7081 fields, which have been split into training and test sets (5551 fields in the train and 1530 fields in the test). For this challenge train and test sets have slightly different crop type distributions. The train set follows the distribution of ground reference data which is a skewed distribution with a few dominant crops being over represented. The test set was drawn randomly from an area weighted field list that ensured that fields with less common crop types were better represented in the test set. The goal was to generate a more uniform distribution of crop types for the test set. You will train your machine learning model on the fields included in the training set and will apply your model to the fields in the test set. You will submit your predictions for the crop type for each of the fields in the test dataset.

The data you will have access to (Satellite imagery and labels) are tiled into 256x256 chips adding up to 1217 tiles. The fields are distributed across all chips, some chips may only have train or test fields and some may have both. Since the labels are derived from data collected on the ground, not all the pixels are labeled in each chip. If the field ID for a pixel is set to 0 it means that pixel is not included in either of the train or test set (and correspondingly the crop label will be 0 as well).

It’s important to know that some fields fall across multiple chips (in both train and test sets), and in this case there will be pixels associated with the same field ID in more than one chip. 

Variables definitions:

The label chips contain the mapping of pixels to crop type labels. The following pixel values correspond to the following crop types:

1 - Wheat
2 - Mustard
3 - Lentil
4 - No Crop/Fallow
5 - Green pea
6 - Sugarcane
8 - Garlic
9 - Maize
13 - Gram
14 - Coriander
15 - Potato
16 - Bersem
36 - Rice
