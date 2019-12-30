## Capstone_Project_IBM_Data_Science - Exploring LA Neighborhoods
This repository contains the capstone project for the IBM Data Science Certificate. 

### Introduction
Los Angeles is one of the most popular cities in the US with diverse population and plenty of social places. It has over 4 million residents, way above Chicago and San Francisco. It is the populous city in California and the second in the US, just below New York City. Moreover, Los Angeles is an incredibly diverse city, home to people from over 140 countries who speak 224 languages that have been identified. Ethnic communities like Koreatown, Chinatown, Thai Town, Little Ethiopia, and Little Tokyo show what a multilingual and cultural city Los Angeles is today. Due to this exist diversity, more and more people from different walks of life are moving to LA. They may be facing big difficulties of choosing neighbohoods. LA is divided into 114 neighborhoods, each with its distinct demographics. Moreover, there are not much information online assiting people learn more about each neighborhood in LA. This project aims to cluster all neighborhoods in LA according to their venues and provide people with some suggestions about each neighborhood.

### Dataset

#### General
Location data is data describing places and venues, such as their geographical location, their category, working hours, full address, and so on, such that for a given location given in the form of its geographical coordinates (or latitude and longitude values) one is able to determine what types of venues exist within a defined radius from that location.So for a given location you will be able to tell if restaurants for example, exist nearby, or if schools, or parks, or gyms, or community centres exist nearby. Also how many of each category exist and how each surrounding venue is reviewed by other people. So this is what's referred to as location data, which is subsutantially used in this project.

#### Case-Specific
This project uses two datasets:
1. I found a dataset containing all geospatial data of LA neighborhoods online. Specifically, this dataset includes names of all neighborhoods, and the boundaries of each neighborhoords. For convenience's sake, I averaged all the boundaries of each neighborhood to get the centered position for each neighborhood. (Feel free to check it out https://s3-us-west-2.amazonaws.com/mappingla.com/downloads/neighborhoods/la_city.json)

2. API data from FourSqaure to get the most common venues of each neighborhood in LA. It is worth to note that there are three neighborhoods that do not have any associated results, so I dropped them for convenience's sake.


### Methodology
I first downloaded and explored the geo-spatial dataset( the first on under the dataset section). As mentioned above, I averages all the boundaries of each neighborhood to get the centered latitude and longitude for each neighborhood. After that, I visualized all neighborhoods on a mapy using package Folium. This map provides us with a brief understanding of locations of all neighborhoods, which is more direct than the original dataset.

Next, Using the above information, I requested FourSquare API for each neighborhood and recorded all venues within each neighborhood. After that, I analyzed each neighborhood according to the distribution of each venue. Specifically, I first dummy coded all the venues and grouped by neighborhood. Therefore, I got the venue information of the each neighborhood, indicating how many certaine venues there are in each neighbrohood. Moreover, for presentation sake, I created another dataset to only keep the first 10 commom venues for each neighborhood. 

Then, I clustered all LA neighborhoods according to their venue information into 6 clusters and visualized these 6 clusters on a map. Besides that, I also explored each cluster carefully and results are shown below. 

### Results
LA neighborhoods can be clustered into 6 clusters, each with some unique characteristics with regards to their venues. 
From the map, we can see that nearby neighborhoords do not necessarily have similary types of venues and are clustered together. Instead, each cluster spreads over a wide range. Let's take a careful examination for some interesting ones below.
1. The First cluster has three neighborhoods. Their most common venues are different types of shops, including sports, cloths and drugstores. This cluster is suitable for those who enjoying shopping and have high commodity demand. 
2. The Third cluster has three neighborhoods. Interestingly enough, their most common venues are parks and yoga studios. This cluster is espeically favorable for those who enjoy life and will take some time every day to exercise.
3. The Fourth cluster contain the most number of neighborhoods. Therefore, their common venues vary a lot across different neighborhoods. However, they generally have restaurants, grocery stores, and some entertaining places. This cluster can satisfy most people's needs. 

### Discussion
This project provide the public a clearer understanding of LA neighborhoods and the distribution of venues within each neighborhoods. However, there are still some shortcomings. For example, the number of clusters is chosen by myself and each cluster makes senes, but there is not strict theorical proof that it is the optimal one. The choice of k can be improved. Please feel free to provide any suggestions. 
