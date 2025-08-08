# Project Setup Instructions

## To Set Up and Run This Project

1. Clone the repository to your local machine using Git:  
   `git clone https://github.com/awillette89/poultry-analytics.git`

2. Navigate to the project directory on your local machine.

3. Create a virtual environment:  
   `python -m venv venv`

4. Activate the virtual environment. See virtual environment commands below.

5. Install the required dependencies from the `requirements.txt` file:  
   `pip install -r requirements.txt`

6. Open `chickens.ipynb` in the browser and run the cells sequentially.

## Virtual Environment Commands

| **Command** | **Windows**                       | **Linux/Mac**                    |
|-------------|-----------------------------------|----------------------------------|
| Create      | `python -m venv venv`             | `python3 -m venv venv`           |
| Activate    | `venv\Scripts\activate`           | `source venv/bin/activate`       |
| Install     | `pip install -r requirements.txt` | `pip install -r requirements.txt`|
| Deactivate  | `deactivate`                      | `deactivate`                     |

## Overview

- This project analyzes egg production and price trends in the United States from 2016 to 2021.
- It uncovers patterns, seasonal variations, and correlations between production volumes and market prices.
- Users can explore data in `chickens.ipynb` with data cleaning, feature engineering, visualizations, and poultry industry insights.
- No coding knowledge is needed to follow notebook explanations, but a Python environment is required to run code.

### Technologies Used

- **Pandas**: Pandas loads, cleans, and manipulates datasets, handles missing values, and creates features.
- **Matplotlib**: Matplotlib generates visualizations like line plots for price trends and bar charts for state production.
- **SQLite3**: SQLite3 stores cleaned data in a database and enables SQL queries for retrieval and joins.
- **Jupyter Notebook**: Jupyter Notebook presents code, comments, and observations in a narrative format.


# Project Objective

- This project investigates the relationship between egg production volumes and market prices across the US from 2016 to 2021.
- **Guiding questions**: What are the seasonal trends in egg production and prices? Which states produce the most eggs?
- **Insight goal**: Uncover trends to inform poultry industry stakeholders on pricing strategies and production planning.

# Data Source

- Data is sourced from the United States Department of Agriculture (USDA) National Agricultural Statistics Service (NASS) Quick Stats database.
- **Egg Prices**: [https://www.nass.usda.gov/Quick_Stats/Lite/#A4980698-4993-3EEA-A05D-C1D0E27DACAA](https://www.nass.usda.gov/Quick_Stats/Lite/#A4980698-4993-3EEA-A05D-C1D0E27DACAA)
- **Egg Production**: [https://quickstats.nass.usda.gov/results/673A75CC-C22C-3B32-A3F5-0AB866AF7F0F](https://quickstats.nass.usda.gov/results/673A75CC-C22C-3B32-A3F5-0AB866AF7F0F)

# Data Dictionary

## Egg Prices Dataset (egg-prices.csv)

- **YEAR (int64)**: contains the year of the data record.
- **LOCATION (object)**: specifies the geographic location, typically US total for aggregates.
- **STATE ANSI (object)**: provides the ANSI code for the state, blank for US total.
- **ASD CODE (object)**: indicates the agricultural statistics district code, blank for US total.
- **COUNTY ANSI (object)**: denotes the ANSI code for the county, blank for US total.
- **REFERENCE PERIOD (object)**: identifies the month of the record.
- **COMMODITY (object)**: specifies the commodity type, which is eggs.
- **ALL UTILIZATION PRACTICES in $ / DOZEN (float64)**: average price per dozen for all practices.
- **ALL UTILIZATION PRACTICES, TABLE in $ / DOZEN (float64)**: average price per dozen for table eggs.

## Egg Production Dataset (egg-production.csv)

- **Program (object)**: specifies the survey program, typically survey.
- **Year (int64)**: ontains the year of production.
- **Period (object)**: identifies the month of production.
- **Week Ending (object)**: provides the week ending date, often blank.
- **Geo Level (object)**: specifies the geographic level, typically state.
- **State (object)**: contains the state name.
- **State ANSI (object)**: provides the ANSI code for the state.
- **Ag District (object)**: specifies the agricultural district, often blank.
- **Ag District Code (object)**: provides the code for the agricultural district.
- **County (object)**: contains the county name, often blank.
- **County ANSI (object)**: provides the ANSI code for the county.
- **Zip Code (object)**: contains the zip code, often blank.
- **Region (object)**: specifies the region, often blank.
- **watershed_code (object)**: provides the watershed code, typically 00000000.
- **Watershed (object)**: ontains the watershed name, often blank.
- **Commodity (object)**: specifies the commodity, which is eggs.
- **Data Item (object)**: provides the data description.
- **Domain (object)**: specifies the domain category, typically total.
- **Domain Category (object)**: specifies the category, typically not specified.
- **Value (object)**: contains the production value and may include (d) for undisclosed.
- **CV (%) (object)**: provides the coefficient of variation, often blank.

# Data Summary

- The egg prices dataset contains 72 rows of monthly US national egg prices from January 2016 to December 2021.
- The average all utilization price is approximately 0.90 $/dozen (minimum: 0.483, maximum: 1.89).
- The average table egg price is approximately 0.66 $/dozen (minimum: 0.197, maximum: 1.81).
- Data types include floats for prices and strings for categorical fields.
- The egg production dataset includes 8,212 rows of state-level monthly production from 2016 to 2021.
- After cleaning, 2,518 rows remain, focusing on production in dozens with undisclosed "(d)" values removed.
- The dataset features quantitative production metrics and qualitative location details for regional trends.
- **Note on missing data**: Some states may appear underrepresented due to "(d)" values. These were removed for accuracy, which may affect completeness. See the notebook’s cleaning steps for details.
- Details are available in `chickens.ipynb`, where data is loaded and explored.