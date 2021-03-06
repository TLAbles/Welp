# Welp. ¯\\\_(ツ)_/¯
Data analysis on one star Yelp reviews.


## Code Louisville Data Analysis Course 1 Spring 2022 

This project uses the Yelp Open Dataset available for educational and academic purposes. Specifically, business and review datasets were accessed, combined, and filtered to find restaurants still in operation. These open restaurants were grouped by review star rating and a histogram was made to visualize the counts of these reviews. The reviews were further filtered to include only one star reviews in English using langdetect. Sentiment analysis was performed on these reviews using Vader, which is designed to detect polarity (how positive or negative text is) and intensity (the strength of the emotion).  Negative, neutral, positive, and compound scores were returned during the sentiment analysis. The compound score, which is a metric that is used to determine how strongly positive or negative reviews are, was added to the data frame. Compound scores can range from -1 (most extremely negative) to +1 (most extremely positive.) The reviews were sorted by compound score with the most negative reviews at the top. Ultimately, only the worst 500 reviews in English were selected to further display. The mean of the compound scores for both the entire dataframe (-0.146) and also the subset of the 500 most strongly negative reviews (-0.995) were calculated to compare how much more strongly negative the subset of the data is compared to the entire dataset. A zoomable base map was created using Folium, a library used to create leaflet maps. The GPS coordinates from the restaurants associated with the reviews with the lowest compound scores were used to add markers to the map. Pop ups were added to each marker with both the name of the restaurant and the text of the review. Words from all of the most negative reviews were then joined, lowercased, and stopwords (a list of the most commonly used words) were removed to make wordcloud displaying the most frequently used words in the negative reviews. 
 
## Setup
Clone this repository.

This project uses Python 3.9.7 

### Requirements
Before starting, install the project's dependencies with
```pip install -r requirements.txt```

If this is unsuccesful due to a missing wordcloud wheel file for your operating system/python version, you can try to install wordcloud with [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) and the remainder with pip by entering these commands into your terminal:

Steps to create a conda environment named welp-env are listed below.

Step 1: Create a conda environment. 

conda create -n yelp-env jupyter notebook 

Step 2: Activate the environment using the command 
conda activate welp-env 

Step 3: Install the packages
```conda install -c conda-forge wordcloud
pip install folium langdetect nltk folium numpy pandas seaborn matplotlib wordcloud langdetect
```

Step 4: After activating the welp-env, check the packages that are installed using the command 
conda list  


Additional information about managing environments can be found here 

https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html

### Environment
This project utilizes Jupyter Notebook and should be displayed using the Jupyter Notebook add on to VS Code. It can be run in a Jupyter Notebook, as well, but some elements may not display quite as intended. 

### Data Sources 
The yelp_business.csv is publicly saved on a Google Drive, and pandas will download it automatically. 

A challenge of using a quite large dataset for this project was determining the best way to store and access the data. The yelp_reviews.csv was too large to host for free on Dropbox or Google Drive, like I did with the yelp_business.csv. It would have been possible to host it on S3, but the potential cost associated with this option made it not a viable solution. I could have performed some preprocessing on the data to reduce its size so it could be publicly saved for free; however, this would have made it difficult to showcase to the reviewers an understanding and ability to manage and manipulate large datasets. 

 The `yelp_review.csv` must be found in the [Kaggle free datasets menu](https://www.kaggle.com/yelp-dataset/yelp-dataset/version/6), downloaded and extracted to your local machine. Replace the existing filepath in the read review file cell with the correct path to load the data. 
 
## Features:

### Category 1: Analyze text and display information about it.
  - Sentiment analysis was performed on reviews, added to df. A mean was also taken based on the compound scores. 
 
### Category 2: Read data from an external file, such as text, JSON, CSV, etc, and use that data in your application.
  - Imported CSVs.  

### Category 3: Visualize data in a graph, chart, or other visual representation of data.
  - Tabular data displayed for review star ratings
  - Histogram displaying star ratings of reviews
  - Markers for restaurants were added to a map using GPS coordinates, business name and review text can be viewed by clicking on     markers.
  - Most frequently used words from negative reviews displayed in wordclouds.

### Category 4:
  - Implement a log that records errors, invalid inputs, or other important events and writes them to a text file.

### Additional features:
  - Use a Jupyter notebook to document your data analysis.
  - Use pandas, matplotlib, and/or numpy to perform a data analysis project. Ingest 2 or more pieces of data, analyze that data in some manner, and display a new result to a graph, chart, or other display.
 