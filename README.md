# Real Estate Linear Regression
![Image by Avi Waxman on Unsplash](Images/avi-waxman-f9qZuKoZYoY-unsplash.jpg)

# Business Understanding
LandingPad Realtors is a real estate business that helps families with school-aged children relocate to King County and find the perfect home to meet their families needs. LandingPad provides potential homeowners with home purchase options within their ideal 
budget. 

* __Stakeholder__: LandingPad Realtors
* __Busines Case__: I have been hired by LandingPad to accurately predict the housing prices within the King County Housing Market. Executives at LandingPad want to launch a multimedia campaign to reach their target audience of young families moving to the Kings County Area and want a reliable model that can be refined over time as more information becomes available. 

Primarily, I will start by identifying the characteristics of homes that increase housing costs. The effect of each relevant feature will then be identified and communicated to the team at LandingPad. This project will be grounded in performing a statistical analysis of the price of houses in the King County House dataset and creating a multiple linear regression model that accurately predicts the sale price of a house in King County.


# Data Undersanding
In this project I will use the CRISP DM method. 
The dataset selected in this project are from the :

* King County House Sales Dataset found in <code>kc_house_data.csv</code>

The dataset can be found in the data folder of this repository along with a file called <code>column_names.md</code> which provides description of the features within the dataset. More information about the features on the site of [the King County Assessor.](https://info.kingcounty.gov/assessor/esales/Glossary.aspx?type=r)

The King County House Sales Dataset includes sales data for 21,597 homes with 20 features including but not limited to:
| Name               | Description                 |Data Type| Categorical or Numeric  |Target or Feature|
|--------------------|-----------------------------|---------|-------------------------|-----------------|
| <code>id</code>    |Unique identifier for a house|int|Numeric|Feature|
* <code>date</code> - Date house was sold
* <code>price</code> - Sale price (__prediction target__)
* <code>bedrooms</code> - Number of bedrooms
* <code>bathrooms</code> - Number of bathrooms
* <code>sqft_living</code> - Square footage of living space in the home
* <code>sqft_lot</code> - Square footage of the lot
* <code>floors</code> - Number of floors(levels) in house
* <code>waterfront</code> - Whether the house is on a waterfront
* <code>view</code>  - Quality of view from house
* <code>condition</code> How good the overall condition of the house is. Related to the maintenance of house. 
* <code>grade</code> -Overall grade of the house. Related to the construction adn design of the house
* <code>yr_built</code> - Year when house was built
* <code>yr_renovated</code> - Year when house was renovated
* <code>lat</code> - Latitude coordinate
* <code>long</code> - Longitude coordinate

# Data Preparation
## Import libraries and Visualization Packages
Importing libraries at the beginning allows access to modules and other tools throughout this project that help to make the tasks within this project manageable to implement. The main libraries that will be used within this project include:

* <code>pandas</code>: a data analysis and manipulation library which allows for flexible reading, writing, and reshaping of data
* <code>numpy</code>: a key library that brings the computationaly power of languages like C to Python
* <code>matplotlib</code>: a comprehensive visualization library
* <code>seaborn</code>: a data visualization library based on matplotlib

## Select Data
Read in data from  <code>kc_house_data.csv</code> using <code>.read_csv()</code> from the pandas library.


## Clean the Data

In order to clean the data, I typically address missing data, place holders and datatypes. This is the most important step of this project because if data is not appropriate for the model, the results will be inherently inaccuarate and my model will result in lackluster predictions. 

To dig deeper into the data, I will:
* Review the datatypes found within the entire dataframe
* Address duplicates, missing and placeholder data
* Address incorrect or incongruous datatypes for the model

# Build a Simple Linear Regression model

First, I will set the dependent variable (<code>y</code>) to be the <code>price</code>.  Next I will choose the most highly correlated features from the dataframe to be the baseline independent variable (<code>X</code>). 
Afterwards, I will:
* Build a linear regression using <code>statsModels</code>
* Describe the overall model performance 
* Interpret its coefficients. 

# Evaluation


# Deployment

# Insights

# Recommendations

# Future Work

# Repository Structure
<pre>
.
└── real_estate_linear_regression/
    ├── README.md
    ├── final_project_phase_2.ipynb
    ├── notebook.pdf
    ├── presentation.pdf
    ├── Images/
    └── .gitignore
</pre>