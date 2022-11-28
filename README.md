# mass-extinction

#Python code and data that was used for the manuscript "How predictable are mass extinction events?" submitted to Royal Society Open Science
#The code and data development was done by William J. Foster, Niklas H. Kitzmann, Jannes Münchmeyer, and Tabea Rettelbach
#28.11.2022

#This code was developed to explore extinction selectivty at the end-Permian, end-Triassic and end-Cretaceous mass extinction events.

#The packages required to run the code are included in each file as the first command

#If you lack coding experience in Python you should be able to run the code using https://mybinder.org/v2/gh/PaleoML/mass-extinction/HEAD and you can also follow the #instructions below
#I recommend downloading python using https://www.anaconda.com/ and the code is written using Jupyter Notebook (Anaconda 3). Once downloaded you can open the files #using Juypter Notebook.

#the notebooks inlcude comments that tell you how the code in each cell works

#data folder conatins the data used for the extinction selectivity analysis for the mass extinction events
#data_20ext contains the data used for the extinction selectivity invesigated for each stage of the study interval, i.e., inlcudes background intervals
#images conatins figures produced by the python code during the analysis
#models conatins the Catboost models produced by the python code
#PBDB_Download inlcudes the vetted .csv files downloaded from the paleobiology database. Changes to the original downloads can be done by comparing the "accepted" #columns with the PBDB database.

#To re-run the analysis in this study:

#01_extinction_analysis.ipynb
#This notebook does a series of different analysis:
#First cell imports all of the required packages
#"Data loading and processing" section organises the data
#"Data exploration" section is a qualitative exploration of the data
#"E_occurrence as a predictor" section explores the impact of removing pre-extinction occurrences as a predictive variable
#"Model training" creates the catboost model for the different mass extinction events
#"Results plotting" provides the figures published in this study, which show the results of the Catboost model
#"Hyperparameter search" explores if the right hperparamters were used in our catboost model
#"Train and export models for SHAP analysis" creates the models required for the shap anlysis in the second code notebook (see below)
#"Number of unique metaspecies" creates the figure to show the extinction probablility of each functional group. In addition,it aves raw values as a new .csv file
#"Recursive feature elimination" investigates the impact of removing features included in the Catboost model, and provides a figure at the end

#02_shap_analysis.ipynb
#First cell imports all of the required packages
#The first 9 cells set up the shap analysis of the Catboost model based on all of the data
#Cells 10 and 11 create a plot to show the summary shap plots for each mass extinction event
#The reminaing cells are for making force plots for each individual functional group. If you want to explore a functional group that is not included, then just change the feature values as instructed on the code comments
#the force plots do not automatically export to the images folder, to save, you must inspect element, then copy the svg attribute and paste that into a text file and save it as an .svg file. You can then open the picture using CorelDraw or Adobe Illustrator.

#03_pca_analysis.ipynb
#First cell imports all of the required packages
#"Data loading and processing" section organises the data
#"Model training" creates the catboost model for each stage (this was not done in 01_extinction_analysis)
#PCA analysis plots the PCA figure
