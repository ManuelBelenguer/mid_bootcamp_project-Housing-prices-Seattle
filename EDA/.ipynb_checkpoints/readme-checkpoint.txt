Introduction

In this notebook will use visual tools, and statistics measures in order to explore the meaningfulness of the independent variables to define the dependent variable.
We'll also append a folder with visualizations done with tableau.


Observations.

    1. Distributions.
        As we can observe in the distribition plots section, althought some have similarity with a bell shape, none of them present a normal distribution. In fact most of them         are quite skewed and present an accentuated curtosis. 
        When training and testing our model, we'll try to see if there is a substancial difference in our results using the variables as they are (without performing any
        transformation, logarithmic transformation or normalization) and using them after performing the mentioned transformations. 
        
        Note: The presence of such skewness indicates that we'll have to deal with significant outliers. As we're treating real state market, this is an unavoidable problem
        that we need to work with.
        
    2. Outliers.
        After doing some boxplots can now see the huge presence of outliers. As pointed above we cannot get rid of them as they're a substancial part of the houses in a city,
        therefore in order to have a better model, we'll probably perform a logarithmic transformation for some of the variables. 
        
        
    3. Correlation.
        If we watch the correlation matrix using pearsons method, we see that some of the variables are more important than the others when predicting the dependent variable. 
        
            Variables correlated above 60% -- > sft_living, grade, sqft_above.
            Variables correlated above 50% -- > bathrooms, sqft_living15.
            Variables correlated above 30% -- > bedrooms, view, sqft_basement, lat.
            Variables correlated above 20% -- > floors, waterfront.
            Variables correlated bellow 20% -- > sqft_lot, condition, yr_built, yr_renovated, zipcode, long, sqft_lot15
            
        Before deciding which are the variables we're keeping we'll perform a variation inflation factor in order to see if some of the independent variables are already 
        definned but others.
        
        
    4. VIF.
        We observe that the VIF indicator for sqft_living and sqft_lot is above the threshold set up at 5. After considering that sqft_living is the variable with the highest
        correlation with the dependent variable we decide to keep and remove sqft_lot from our dataset.
        
        We still see moderate high multicollinearity in the sqft_living variable, we're going now to remove the variable 'bathrooms' as is kind of high correlated.
        
        After removing sqft_lot and bathrooms from the dataset no VIF is above the set threshold. Therefore this are the variables we're keeping to train our model:
        
            - bedrooms
            - bathrooms
            - sqft_living
            - floors
            - waterfront
            - view
            - condition
            - grade
            - sqft_above
            - sqft_basement
            - yr_built
            - yr_renovated
            - zipcode
            - lat
            - long
            - sqft_living15
            - sqft_lot15
        
       
        
        
The following link takes you to my TableauPublic where additional EDA has been performed in order to have a better understanding of the data we're dealing with.
  
  
          https://public.tableau.com/profile/manuel1984#!/vizhome/house_price_Seattle/Historia1?publish=yes
