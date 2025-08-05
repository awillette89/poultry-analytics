# Project Setup Instructions
## To set up and run this project:

### Clone the repository to your local machine using Git:
git clone https://github.com/awillette89/poultry-analytics.git

### Navigate to the project directory:
cd poultry-analytics

### Create a virtual environment (recommended Python 3.12 or later):
python -m venv venv

### Activate the virtual environment:

On Windows: venv\Scripts\activate
On macOS/Linux: source venv/bin/activate


### Install the required dependencies from the requirements.txt file:
pip install -r requirements.txt

### Launch Jupyter Notebook.

### Open chickens.ipynb in the browser and run the cells sequentially.

This project analyzes egg production and price trends in the United States from 2016 to 2021. By examining data on table egg production and monthly prices, we identify patterns, seasonal variations, and potential correlations between production volumes and market prices. Once running, the user can expect a narrative-driven exploration in the Jupyter Notebook, including data cleaning, feature engineering, visualizations, and insights into the poultry industry. No coding knowledge is required to follow the explanations, though running the code requires a Python environment.
Technologies Used

Pandas: Used to load, clean, and manipulate the datasets, such as handling missing values and creating new features for analysis.
Matplotlib/Seaborn: Employed to generate visualizations like line plots for price trends and bar charts for production by state.
SQLite3: Integrated to store cleaned data in a database, enabling SQL queries for efficient data retrieval and joins.
Jupyter Notebook: The primary development tool for presenting code, explanations, and results in a cohesive, narrative format.

# Data Source
The data is sourced from the United States Department of Agriculture (USDA) National Agricultural Statistics Service (NASS) Quick Stats database.

#### Egg Prices: https://www.nass.usda.gov/Quick_Stats/Lite/#A4980698-4993-3EEA-A05D-C1D0E27DACAA
#### Egg Production: https://quickstats.nass.usda.gov/results/673A75CC-C22C-3B32-A3F5-0AB866AF7F0F

# Data Dictionary
Egg Prices Dataset (egg-prices.csv)

YEAR: The year of the data record (integer, e.g., 2016).
LOCATION: The geographic location, typically "US TOTAL" for national aggregates (string).
STATE ANSI: ANSI code for the state, blank for US total (string).
ASD CODE: Agricultural Statistics District code, blank for US total (string).
COUNTY ANSI: ANSI code for the county, blank for US total (string).
REFERENCE PERIOD: The month of the record (string, e.g., "JAN").
COMMODITY: The commodity type, always "EGGS" (string).
ALL UTILIZATION PRACTICES in $ / DOZEN: Average price per dozen for all egg utilization practices (float).
ALL UTILIZATION PRACTICES, TABLE in $ / DOZEN: Average price per dozen for table eggs specifically (float).

Egg Production Dataset (egg-production.csv)

Program: The survey program, typically "SURVEY" (string).
Year: The year of production (integer).
Period: The month of production (string).
Week Ending: Ending date of the week, often blank (string).
Geo Level: Geographic level, e.g., "STATE" (string).
State: The state name (string).
State ANSI: ANSI code for the state (string).
Ag District: Agricultural district, often blank (string).
Ag District Code: Code for agricultural district (string).
County: County name, often blank (string).
County ANSI: ANSI code for the county (string).
Zip Code: Zip code, often blank (string).
Region: Region, often blank (string).
watershed_code: Watershed code, typically "00000000" (string).
Watershed: Watershed name, often blank (string).
Commodity: The commodity, "EGGS" (string).
Data Item: Description of the data, e.g., "EGGS, TABLE - PRODUCTION, MEASURED IN DOZEN" (string).
Domain: Domain category, "TOTAL" (string).
Domain Category: Category, "NOT SPECIFIED" (string).
Value: The production value, may include "(D)" for undisclosed (string).
CV (%): Coefficient of variation, often blank (string).

# Data Summary
The egg prices dataset contains 72 rows covering monthly US national egg prices from January 2016 to December 2021. Key statistics include:

Average all utilization price: ~0.90 $/dozen (min: 0.483, max: 1.89).
Average table egg price: ~0.66 $/dozen (min: 0.197, max: 1.81).
Data types: Mostly floats for prices, strings for categorical fields.

The egg production dataset includes 8,212 rows for state-level monthly production in 2016-2021, with values in dozens or individual eggs for hatching and table types. After cleaning, 2,518 rows remain, focusing on production measured in dozens. Production volumes vary by state, with some values initially undisclosed "(D)" removed. It features quantitative production metrics and qualitative location details, enabling analysis of regional trends.
Note on Missing Data: Certain states may appear underrepresented or absent in visualizations and analysis due to undisclosed production values marked as "(D)" in the original dataset (e.g., for states like Arkansas or California in specific months). These were removed during cleaning to ensure data accuracy, but this may affect completeness for those regions. Refer to the notebook's cleaning steps for details.
For more details, refer to the chickens.ipynb notebook where data is loaded and explored.

# Project Objective

Investigate the relationship between egg production volumes and market prices across the US from 2016 to 2021.
Guiding Question: How do seasonal and state-level production changes correlate with price fluctuations for all egg types and table eggs specifically?
Insight Goal: Uncover trends that could inform poultry industry stakeholders about pricing strategies and production planning.

# Additional Resources

Rubric: https://docs.google.com/forms/d/e/1FAIpQLScNWu_WNJLF0wK-BUuu9JsBGnxFjS72SQmM4Jd5Wy7JngWjug/viewform
Guidelines: https://docs.google.com/document/d/1fkQFPHQ_80L_xpG3EucxybTVFM556pn0YtlWa0n8Ju0/edit?tab=t.0
Interview Information: https://docs.google.com/document/d/1gumZocblkZjVEG3G96DD-msB8mhJux7GiiCyg47uY24/edit?tab=t.0#heading=h.5i7odw1grzjo