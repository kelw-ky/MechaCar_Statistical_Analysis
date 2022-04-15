# MechaCar_Statistical_Analysis

## Overview 

The following analysis was done using "MechaCar_mpg.csv" and "Suspension_Coil.csv". Example of part of the data is shown below. 

<p float="left">
    <img src="/Resources/mechaCar_mpg.png"/>
    <img src="/Resources/suspension_coil.png"/>
</p>


## Linear Regression to Predict MPG

The Vehicle Length and ground clearance were the two coefficients which provided non-random amount of variance, as these two variables has a p-value smaller than 0.05. The slope of the linear model is not considered to be zero. Since, some independent variable (vehicle_length, ground_clearance, and AWD) has significant effect as shown below; the slope of this curve will not be zero. We can see that the R-squared is 0.7149 and the Adjusted R-squared is 0.6825. This means that the output could be explained by this formula 68% to 71%, which is pretty accurate. 

![Linear Summary](/Resources/linear_summary.png)


## Summary Statistics on Suspension Coils

When looking at the Total Summary chart, the variance shows 62.29356 pounds, which falls into the suggested variance of 100 pounds and would meet the design specification. In the Lot Summary chart, Lot1, Lot2 and Lot3 has a variance of 0.9795918, 7.4693878, and 	
170.2861224 respectively. Lot1 and Lot2 would meet the design specification as it is under 100 but since Lot3 is above the 100 pounds, they would not meet the specification. Only Lot1 and Lot2 should use this design but Lot3 will need a different one. 

<b>Total Summary</b>

![Total Summary](/Resources/total_summary.png)

<b>Lot Summary</b>

![Lot Summary](/Resources/lot_summary.png)


## T-Tests on Suspension Coils

Using "t.test(suspension_coil$PSI,mu=1500)", there is a p-value = 0.06028, which is higher than the significance level of 0.05. This means that we fail to reject the null hypothesis. Looking at the mean, the 1497.5 is very close to the estimated mean of 1500. 

![t.test](/Resources/ttest.png)

Below, we can see the t.test for each of the lots. The p-value of lot1, lot2, and lot3 are 1, 0.6072, and 0.04168; we failed to reject the null hypothesis for lot1 and lot2 since it is greater than the significance level of 0.05, but lot3 is 0.04168 and hence we would reject the null hypotheses. We can also see that the mean of each lot (lot1 - 1499.719, lot2 - 1499.423 and lot3 - 1492.431); lot1 and lot2 are significantly closer to the estimated mean of 1500 than lot3 is. 

![Lot t.test](/Resources/ttest_subset.png)


## Study Design: MechaCar vs Competition

The metrics would want to test would be the Selling Price, Gas Efficiency and City Types (Urban, Suburban, and Rural). 


|  Metrics            |  Variable      |
| ------------------- | -------------- |
|  Horse Power/Engine |  Independent   |
|  Fuel Efficiency    |  Dependent     |
|  City Types         |  Independent   |


<u>The Null and Alternative Hypothesis</u>

- Null Hypothesis: Would a higher horse power and one's city types affect the fuel efficiency of the car in a postive way? 
- Aternative Hypothesis Would a higher horse power and one's city types affect the fuel efficiency of the car in a negative way? 

I would use an ANOVA test to analyze the different horse powers in different city types and how fuel efficient the cars are. Using ggplot2 for visuals would allow readers to easily see the analysis and if there is a trend between these variables. The data I would need would be 10 cars, each with a different horse power (3 levels- low, medium and high) and driving in the 3 different city types (urban, suburan, and rural). We would limit this to only the summer season as the fuel efficiency would be different in different seasons. 

