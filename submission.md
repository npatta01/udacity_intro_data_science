
# 1.  Statistical Test

#### 1.1 Which statistical test did you use to analyse the NYC subway data? Did you use a one-tail or a two-tail P value? What is the null hypothesis? What is your p-critical value?

The question we are interested in asking is if rain affects the riderhsip.
So, we are interested if the ridership increases or decreases.

The null hypothesis is that there is no difference in riderhip on rainy and non-rainy days.

So, to disprove the hypothesis we just need to show that riderhip is higher or lower on rainy days.
The p-value obtained using the Mann Whitney-u test was 5.48269387142e-06.

#### 1.2 Why is this statistical test applicable to the dataset? In particular, consider the assumptions that the test is making about the distribution of ridership in the two samples.

The distribution of hourly ridership is not uniform, so we can't apply the student t-test.

Instead we have to use the Mann Whitney-u test since it doesnot assume that the data comes from a normal distribution.



#### 1.3 What results did you get from this statistical test? These should include the following numerical values: p-values, as well as the means for each of the two samples under test.


The double sided p-value obtained was 5.48269387142e-06.

The mean entries per hour when not raining is  1845.53943866
The mean entries per hour when raining is  2028.19603547



#### 1.4 What is the significance and interpretation of these results?

The p-value is lower than the usually accepted value of 0.05.
s
What this shows is there is a significant difference between ridership on rainy and non-rainy days.




# Section 2. Linear Regression

#### 2.1 Model Used
The model used was the gradient descent covered in exercise 3.53943866

#### 2.2 Features used
The features used are 
- 'rain' :  boolean, weather it is raining or not
- 'precipi' : precipitation in inches
- 'hour': time (0,4am,8am,12,4pm,8pm)
- 'meantempi': average temperature in location
- 'day_week': value from 0 - 6 indicating day

The dummy unit 'Unit' was used.

#### 2.3 Reason for choosing model
I chose the features ('rain', 'hour','day of week') based on exploration of data.
There does seem to be a correlation between those features.

I choose the features 'precipi' because I thought that the amount of moisture would determine wether people decided to take the subway/walk/take a car.

I also choose the feature 'meantempi', because I wanted to capture the idea that average weather in a place might affect ridership. Maybe if the weather is usually bad, it won't affect ridership. 



#### 2.4 Coefficeints of regression
- Rain theta : 44.6019765193
- Precipitaion theta: -94.6538058653
- Hour theta: 848.05500503
- Mean temp theta: -108.220263124
- Day of week theta: -306.170658311
- One theta: 1886.52382521


#### 2.5 What is your model’s R2 (coefficients of determination) value?
The R^2 was 0.47130570988255771

#### 2.6 What does this R2 value mean for the goodness of fit for your regression model? Do you think this linear model to predict ridership is appropriate for this dataset, given this R2  value?

R squared ranges from 0 to 1. We see that the predictive power of our model still can't explain all the variance.
Looking at the costhistory graph, our model can't improve with the current features

So, we might need to do some feature engineering (polynomial regression)

I think I should have choosen a different cost function. Instead of the cost being  the difference between between predicted and actual, I should have rounded by 100 or even thousand. No model would be able to accurately predict to the nearest 1 person.


#Section 3: Visualization 

My ipython notebook has three visualizations:

- Total entries/exits per hour by day across all stations
- Total entries/exits by hour across all stations
- Comparision of entries by hour ofr rainy nad non-rainy days


# Section 4. Conclusion

#### 4.1 - 4.2  Comment on analysis

I am surprised by my finding. My visualizations and model seems to suggest that when it is raining, that less people ride the subway. The significantly low p-value and about double the riderhip on non-rainy days, seems to imply that more people indeed prefer those conditions when riding the subway.

I feel that the conclusion is counterintuitive. In my own limited experience in NYC, I felt I experienced the subway beings more crowded.  

But according to this data-set less people ride the subway on rainy days.

The conclusion is based on the less than 0.05 p-value for the two tailed null-hypothesis that there is no difference. Because we got a value below that, we know that there is indeed a statistically significant relationship between ridership and raining, although we are not sure of which direction. 

Looking at the charts, we can see see that riderhip is less on rainy days

# Section 5. reflection

#### 5.1 Shortcomings
I wish the dataset had entries/exits per hour. Because the data is grouped by a 4hr interval, data such as during peak hours (morning, evening) are lumped together.

My charts graphed the summation of riderhsip by hour/day. I feel it would have been meaningful to have average ridership per individual station.

I think instead of using mean temperature and precipitation, I should have used calculated the average temperature/precipitation for each station and then calculated the difference form the average. This would better capture how drastic the weather was on average.     
  

https://docs.google.com/document/d/16T3kirC0IxvtfxlZb7n5kOz5xFF_JTwrG31J2OZj8KM/pub
