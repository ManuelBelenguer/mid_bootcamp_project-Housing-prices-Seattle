For our model building we decided to use a Linear Regression model. We followed different approaches :

1. A first approach using the selected variables bellow the threeshold (at 5) after doing the variation inflation factor (VIF).
    - dummification of the variables "grade" and "zipcode".
    - using numerical data without any standarizing, normalizing or log transforming.
    
    Results:
    
                           Mean Absolute Error: 90301.911
                           Mean Squared Error: 21502364356.073
                           Root Mean Squared Error: 146636.845
                           R2: 0.842  
                           Adjusted R2: 0.841
                           
                           
                           
2. On a second approach we try to see if the model performance was improving by removing certain numerical variables that might be repetitive:
    - same process than on the previous approach removing the numerical variable "sqft_living15".
    
    Results:
    
                           Mean Absolute Error: 90358.827   
                           Mean Squared Error: 21542900905.254   
                           Root Mean Squared Error: 146775.001
                           R2: 0.842  
                           Adjusted R2: 0.841
                           
       
       
            - We observe no improvement in our model, actually MAE, MSE and RMSE increase. 
            
            
            
3. On a third approach we decided to extract a more significant meaninfulness for the location variables (latitude, longitude). The way to do this was to calculate the distance from each of the properties to points of interest in the city of Seattle such as center. 
    - get location from center of Seattle and center of Bellevue.
    
        Results:
    
                           Mean Absolute Error: 90301.911      
                           Mean Squared Error: 21502364356.073      
                           Root Mean Squared Error: 146636.845   
                           R2: 0.842  
                           Adjusted R2: 0.841
                           
                           
                           
             - By doing this approach we get the same results than on the first approach. 
             
             
             
4. On a fourth and final approach we performed a logarithmic transformation for the variables "sqft_living", "sqft_lot" and " price".
    - We still keeped the distance from each property to points of interest. (This might be a not very useful action as it doesn't improves the model, and it will be more cost effective).
        
        Results:
    
                           Mean Absolute Error: 71946.599        
                           Mean Squared Error: 15112286722.271      
                           Root Mean Squared Error: 122932.041   
                           R2: 0.889    
                           Adjusted R2: 0.888
                           Relative Error: 0.133
                           
                           
                           
              - With these results we assume that the model cannot be improved. R2 and Adjusted R2 metrics show that our model have an overall good performance. On the other 
              hand, MAE and RMSE show that for some of the houses the error we'll see is going to be high. These cases will refer to outliers. Note that these outliers where
              the model doesn't perform so good are not the ones that are above the Q3, they're actually bellow Q1 which makes us conclude that our model is not good predicting
              houses with a low price. 
              - We get a relative error of 0.133, we're some prediction we're very accurate while others weren't. In the notebook you'll find a plot showing what kind of house
              (based on price) were better predicted. A more detailed plot can be found in the following link:
              
                                  https://public.tableau.com/profile/manuel1984#!/vizhome/HousepricesSeattlerel_error/Hoja1?publish=yes
                           
                           
                           
    
    
                               
       