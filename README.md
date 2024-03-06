# dsc-phase-2-project
Overview  
This is a data analysis to help real estate agents provide guidance to clients on what renovations might increase the value of their homes and by what amount.
Link to Notebook:
Link to Presentation: 


Business and Data Understanding  

Homeowners who are looking to potentially sell their houses want to make investments that will maximize the value of their home when they are ready to sell. By analyzing home sales in the Kings County area of Washington, I will look at the attributes that contribute most to the sale price.


Explain your stakeholder audience here  
Realtors would be able to add value to their clients by providing insights into what the homeowner can do to increase the potential sale amount.

Data Understanding
This project uses the King County House Sales dataset. It contains many fields, with the key ones being the sales date, price, number of bedrooms, number of bathrooms, square feet of living space, lot square footage and number of floors. There are other fields such as being near a greenbelt or having a view, which a homeowner cannot change.

Methodology

1. Data importing and initial viewing
2. Data cleaning
3. Model creation and iteration
4. Visualizations to support recommendations

Modeling  

First I took a look at the correlation across all of the numeric variables and created a simple linear regression with square footage of living space, since that had the highest correlation to sales price. This gave me an r-squared of 0.374, so I created a second model that included the number of bathrooms, which had the second highest correlation to sales price. This gave me an r-squared of .375, which is just a modest improvement.

Then I created a third model, which added all of the numeric fields into a multi-variable linear regression, and this only improved the r-squared to 0.411.

Finally, I added in a feature to code the sales date to a season - winter, spring, summer or fall. Then I used the get dummies function to convert season from a categorical field into a numeric field through one-hot encoding. This resulted in an r-squared of 0.766, which is almost 2x improvement. The p-value for the model is 0, which is statistically significant.


Regression Results  

Looking at the initial regression results, this seems to be a model that can explain 76% of the sales price. However, the p-value for the summer_sold variable is greater than 0.05, at 0.07, meaning there's a 7% probability that the results are accidental.
Conclusion  

