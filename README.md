# A Crash Look at England's Road Traffic Accident Data

# Motivation

Road traffic accidents are taking a serious toll on our lives and our communities.
In this project I'm trying uncover some factors and patterns contributing to accidents and the severity of an injury.
Specifically, I try to answer the following questions:
 - How has the number of accidents and severity of accidents change over the last 5 years?
 - What is the distribution of the age groups and gender of the driver of vehicles involved in accidents?
 - Are certain vehicle types or road classes more dangerous?
 - Are injuries tend to be more serious in certain environmental conditions?
 - Where are the accident hot-spots?

# Data
This project is using [Road Safety Data](https://data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data) published by the [Department for Transport](https://www.gov.uk/government/organisations/department-for-transport) (DfT)

The data is not duplicated in this repo, it can be accessed here: https://data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data

The data is provided in three tables with a relationship to each other. The data used covers a 5 year period starting 2015 and provides data about the circumstances of personal injury road accidents in Great Britain (England, Scotland and Wales). The encoding of the categorical columns is provided in the [data guide](http://data.dft.gov.uk/road-accidents-safety-data/variable%20lookup.xls) spreadsheet.

The data went through some processing prior to the analysis undertaken to answer the above questions:
 - Categorical columns were converted to Pandas category type
 - certain columns were joined accross different tables
 - rows with missing values were dropped

# summary of the results of the analysis

1. How has the number of accidents and severity of accidents change over the last 5 years?

    The number of accidents are generally decreasing. however the number of fatalities constant, the serious injuries have increased, only the slight injuries have decreased
    
2. What is the distribution of the age groups and gender of the driver of vehicles involved in accidents?

    Age distribution follows a similar pattern for both men and women with a peak between 20 - 35, however twice as much male driver is involved in an accident then female drivers.
    
3. Are certain vehicle types or road classes more dangerous?

    Injuries of an accident with a motorbike has higher Killed or Seriously Injured (KSI) proportion
    
4. Are injuries tend to be more serious in certain environmental conditions?
    
    There's no single environmental factor highlighted by the analysis. The KSI proportion is higher when two or more environmental factor is less favourable (reduced visibility and reduced friction along the road surface).

5. Where are the accident hot-spots?
    
    The coordinates (Easting and Northings in meters) and density based clustering was used to highlight the hot-spots.
    Scikit-learn DBSCAN implementation was used with a range of eps and min_samples monitoring the size and number of the clusters.
    The clusters identified shared via this Plotly Chart Studio map: https://plotly.com/~jeneigabor/13/

The detailed discussion can be read on [medium](https://gaborjenei.medium.com/a-crash-look-at-englands-road-traffic-accident-data-62049d4d95b):
https://gaborjenei.medium.com/a-crash-look-at-englands-road-traffic-accident-data-62049d4d95b

# Libraries
- Processing: [NumPy](https://numpy.org/), [Pandas](https://pandas.pydata.org/)
- Modelling [scikit-learn](https://scikit-learn.org/stable/)
- Visualisation: [matplotlib](https://matplotlib.org/), [seaborn](https://seaborn.pydata.org/), [Plotly](https://plotly.com/python/)

The exact version can be found in the requirements.txt

# Files 
 - Udacity DSND Project1_BlogPost.ipynb is the jupyter notebook holding all code with the analysis
 - variable lookup.xls is the data dicitionary describing the variables
 - requirements.txt is the file listing the packages and their versions I used
 - Data folder has all the raw data files
