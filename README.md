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
| Name               | Description                 |Final Datatype|Numeric or Categorical|Target or Feature|
|--------------------|-----------------------------|---------|-------------------------|-----------------|
| <code>id</code>    |Unique identifier for a house| <code>int</code>|Numeric|Feature|
|<code>date</code>| Date house was sold|<code>datetime</code>|Numeric|Feature|
| <code>price</code>|Sale price (__prediction target__)|<code>int</code>| Numeric|Target|
| <code>bedrooms</code>|Number of bedrooms|<code>int</code>|Numeric|Feature|
| <code>bathrooms</code>|Number of bathrooms|<code>float</code>|Numeric|Feature|
| <code>sqft_living</code>|Square footage of living space in the home|<code>int</code>|Numeric|Feature|
| <code>sqft_lot</code>|Square footage of the lot|<code>int</code>|Numeric|Feature|
| <code>floors</code>|Number of floors(levels) in house|<code>float</code>|Numeric|Feature|
| <code>waterfront</code>|Whether the house is on a waterfront|<code>float</code>|Categorical|Feature|
| <code>view</code>|  Quality of view from house|<code>float</code>|Categorical|Feature|
| <code>condition</code>|How good the overall condition of the house is. Related to the maintenance of house|<code>int</code>|Numeric|Feature| 
| <code>grade</code>|Overall grade of the house. Related to the construction and design of the house|<code>int</code>|Numeric|Feature|
| <code>yr_built</code>|Year when house was built|<code>int</code>|Numeric|Feature|
| <code>yr_renovated</code>|Year when house was renovated|<code>int</code>|Numeric|Feature|
| <code>lat</code>|Latitude coordinate|<code>float</code>|Numeric|Feature|
| <code>long</code>| Longitude coordinate|<code>float</code>|Numeric|Feature|

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
* Explore correlation between features

# Build a Simple Linear Regression model

First, I set the dependent variable (<code>y</code>) to be the <code>price</code>.  Then I chose the most highly correlated features from the dataframe to be the baseline independent variable (<code>X</code>). 
Finally, I followed this methodology:
* Build a linear regression using <code>statsModels</code>
* Describe the overall model performance 
* Interpret its coefficients. 
![Simple_Linear_model_trendline](https://user-images.githubusercontent.com/107881738/213949424-e1fcb21d-015f-4692-a90f-d59301ab121a.png)


# Evaluation
This simple linear regression model is statistically significant overall, and explains 36.5% of the variance in house price. Both the intercept and the coefficient for sqft_living are statistically significant.

The intercept is a small negative number, meaning a home with 0 square feet of living would cost around $0.

The coefficient for sqft_living is about 157, which means that for each additional square foot of living space, I expect the price to increase about $157.

The results Summary from the statsmodel ordinary least squares shows:

![OLS_regression_simple](https://user-images.githubusercontent.com/107881738/213949522-674e75a2-aec9-46cb-93c3-a0c88791e406.png)

# Insights
## Q1. Which neighborhoods have the highest average home price?
***
For the first question I looked for correlations between attributes and used price as my target variable. I explored data related to this question using visualizations created with <code>seaborn</code>, <code>plotly express</code> and <code>matplotlib</code>.
![Housing Prices in King County_edit_edit](https://user-images.githubusercontent.com/107881738/213952477-9ed3cedf-bbad-42e9-b589-4fa6219d4713.gif)

## Q2.  How does the number of bedrooms affect the sale price of a home?
***
For the second question, I removed features with high p-values and correlations, truncated the data so that it was more suitable for a linear regression model: 
- linear : one or more predictor features have a linear relationship with the target
- normal : one or more features (random variables from the data) all have a bell shaped curve
- homoscedasticity : little to no multicollinearity (highly correlated variables) . I explored data related to this question using visualizations created with <code>seaborn</code>, <code>plotly express</code> and <code>matplotlib</code>.

![Q2_visualization](https://user-images.githubusercontent.com/107881738/213952841-a11ae768-3802-4085-9780-d9003a7c13b0.png)

## Q3. How does proximity to a highly rated school affect the sale price of a home?
***
For the third question, I used data from the greatschools website and created a function that calculated the closest distance to a school that was rated Above Average or higher (betwen 7 and 10, inclusive):
![Q3_visualization](https://user-images.githubusercontent.com/107881738/213953720-5cbd3afa-2a1d-4f61-9440-165493e9c79b.png)

# Recommendations
- Curate a set of listings using the interactive map that are a between 2 and 5 bedroom homes.

- Use the interactive map to narrow down homes that have a minimum sale price of 470K dollars.

- Show families homes that and are within 10 miles of an Above Average school. This will allow Landing Pad to reach a broader set of home owners who are within our target market.

# Future Work
Moving forward I would like to explore the effect of distance to local attractions (ex. parks, third places, places of worship) on sale price in the King County dataset.
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
