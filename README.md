# Welp. ¯\\\_(ツ)_/¯
Data analysis on one star Yelp reviews.


## Code Louisville Data Analysis Course 1 Spring 2022 

This project uses the Yelp Open Dataset available for educational and academic purposes. Specifically, business and review datasets were accessed, combined, and filtered to find restaurants still in operation. These open restaurants were grouped by review star rating and a histogram was made to visualize the counts of these reviews. The reviews were further filtered to include only one star reviews in English using langdetect. Sentiment analysis was performed on these reviews using Vader, which is designed to detect polarity (how positive or negative text is) and intensity (the strength of the emotion).  Negative, neutral, positive, and compound scores were returned during the sentiment analysis. The compound score, which is computed by normalizing negative, neutral, and positive scores, was added to the dataframe. A zoomable base map was created using Folium, a library used to create leaflet maps. The GPS coordinates from the restaurants associated with the reviews with the lowest compound scores were used to add markers to the map. Pop ups were added to each marker with both the name of the restaurant and the text of the review. Words from all of the most negative reviews were then joined, lowercased, and stopwords (a list of the most commonly used words) were removed to make wordcloud displaying the most frequently used words in the negative reviews. 
 
## Setup
Clone this repository.

### Requirements
Before starting, the following packages will need to be installed:

```
conda install -c conda-forge wordcloud
pip install folium langdetect nltk folium numpy pandas seaborn matplotlib wordcloud langdetect
```
### Environment
This project utilizes Jupyter Notebook and should be displayed using the Jupyter Notebook add on to VS Code. 

### Data Sources 
The yelp_business.csv is publicly saved on a Google Drive, and pandas will download it automatically, but the `yelp_review.csv` must be located at the [data source](https://www.kaggle.com/yelp-dataset/yelp-dataset/version/6) and downloaded and extracted to a local machine. Replace the existing filepath to the downloaded file in the ‘ ‘ in the #read review file cell with the correct path to load the data. 
 
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
 