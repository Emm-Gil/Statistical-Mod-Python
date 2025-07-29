# Statistical Modelling with Python
:star:*Emma Gilbert*:star:


## Project/Goal

The goal of this project was to explore and quantify the relationship between bike availability and nearby Points of Interest (POIs) in Philadelphia 🦅 **Go Birds** 🦅
The project provided an opportunity to further develop Python, SQL and API skills, and to build a linear regression model using statsmodels.


## Process

### 1. Set Up

- Retrieved Philadelphia bike station data via CityBikes API
- Collected POI data from FourSquare and Yelp APIs using station coordinates
- Stored raw and cleaned versions of datasets as `.csv` files in a working data folder
- Set up a local SQLite database to assist in data validation
  
### 2. Data Cleaning

- Removed unnecessary columns like redundant index fields
- Standardized naming conventions across datasets
- Added a source column to distinguish Foursquare from Yelp data
- Dropped duplicate POIs based on name and location to avoid data skew
- Filtered raw data to idenitfy only POIs related to the food and beverage industry

### 3. Data Merging

- Merged cleaned POI data with bike station data on station name
- Ensured Yelp data was prioritized where available, due to its completeness
    - Yelp data included ratings and number of reviews, FourSquare did not
- Exported the final merged dataset as `combined_all.csv`
- Used SQL joins to validate data and confirm successful integration of all sources

### 4. Feature Engineering

- Created a summary table of each station’s POI count and number of available bikes
- Added new variables for:
    - Average Yelp rating per station
    - Total review count per station

### 5. Regression Modeling

- Built a linear regression model to predict number of bikes based on:
    - POI count
    - Average rating (Yelp only)
    - Review count (Yelp only)
- Evaluated multiple versions of the model to test which features contributed meaningfully
- Interpreted R-squared, p-values, and coefficients to draw insight

### 6. Build README and Upload ERD

- Created a `README.md` file to summarize project goals, steps, wins and opportunities
- Used Git and GitHub to track changes and submit the final version
- Uploaded ERD to the repo

## Tools Used

- Python
    - Pandas
    - NumPy
    - statsmodels
    - Seaborne
    - Matplot Lib
- SQLite
- Jupyter Notebook
- Git & GitHub
- APIs
    - CityBikes
    - Yelp
    - FourSquare

## Project Wins

- Successfully merged multi-source API data and joined with local bike station data
- Performed validation steps using both SQL and Python
- Built multiple regression models and interpreted results
- Practiced resolving real-world issues with data (nulls, duplicates, inconsistent fields)

## Project/Personal Opportunities

- Realized the impact of overly aggressive data cleaning on model input size
- Encountered time trade-offs between completeness and precision when filtering POIs

## Future Goals

- Improved regression model by revisiting and more rigorously cleaning categories data
- Expanding outside the food and beverage filter
    - Large Capacity Venues (arenas, sports fields)
    - Education establishments (University Campus, Schools)
- Improved database and overall cleaning
