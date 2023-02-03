# MechaCar_Statistical_Analysis

## Overview of Project
A few weeks after starting his new role, Jeremy is approached by upper management about a special project. AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on Jeremy and the data analytics team to review the production data for insights that may help the manufacturing team.

In this challenge, you’ll help Jeremy and the data analytics team do the following:

* Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes
* Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots
* Run t-tests to determine if the manufacturing lots are statistically different from the mean population
* Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. For each statistical analysis, you’ll write a summary interpretation of the findings.


## Deliverables:
This new assignment consists of three technical analysis deliverables and a proposal for further statistical study. You’ll submit the following:

* Data Source: `MechaCar_mpg.csv` and `Suspension_Coil.csv`
* Data Tools:  `tidyverse`, `dplyr`, `ggplot2` and `MechaCarChallenge.RScript`.
* Software: `RStudio` and `R`

# Deliverable 1:  
## Linear Regression to Predict MPG
### Deliverable Requirements:

The `MechaCar_mpg.csv` dataset contains mpg test results for 50 prototype MechaCars. The MechaCar prototypes were produced using multiple design specifications to identify ideal vehicle performance. Multiple metrics, such as vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance, were collected for each vehicle. Using your knowledge of R, you’ll design a linear model that predicts the mpg of MechaCar prototypes using several variables from the `MechaCar_mpg.csv file`. 

> To Deliver. 

- The `MechaCar_mpg.csv` file is imported and read into a dataframe
- An RScript is written for a linear regression model to be performed on all six variables
- An RScript is written to create the statistical summary of the linear regression model with the intended p-values
- There is a summary that addresses all three questions


#### Results on Deliverable:
**Resulting Model:** 

### mpg =  (6.267)**vehicle_length** + (0.0012)**vehicle_weight** + (0.0688)**spoiler_angle** + (3.546)**ground_clearance** + (-3.411)**AWD** + (-104.0)
				

**Statistical Summary:** 
![d1](https://github.com/Hanzian/MechaCar_Statistical_Analysis/blob/main/Pictures/linear%20regression.png)

From the above output we can see that:

1. The **vehicle length**, and **vehicle ground clearance** are statistically likely to provide non-random amounts of variance to the model. That is to say, the vehicle length and vehicle ground clearance have a significant impact on miles per gallon on the MechaCar prototype. Conversely,
the **vehicle weight**, **spoiler angle**, and **All Wheel Drive** (AWD) have p-Values that indicate a random amount of variance with the dataset.  

2. The p-Value for this model, ```p-Value: 5.35e-11```, is much smaller than the assumed significance level of 0.05%. This indicates there is sufficient evidence to **reject our null hypothesis**, which further indcates that the slope of this linear model is **not zero**.


3.  This linear model has an r-squared value of 0.7149, which means that approximately 71% of all mpg predictions will be determined by this model. Relatively speaking, his multiple regression model **does predict mpg of MechaCar prototypes effectively**. 

# Deliverable 2:  
## Summary Statistics on Suspension Coils
### Deliverable Requirements:

The MechaCar Suspension_Coil.csv dataset contains the results from multiple production lots. In this dataset, the weight capacities of multiple suspension coils were tested to determine if the manufacturing process is consistent across production lots. Using your knowledge of R, you’ll create a summary statistics table to show:

- The suspension coil’s PSI continuous variable across all manufacturing lots
- The following PSI metrics for each lot: mean, median, variance, and standard deviation.

#### Technical Analysis
1. Download the `Suspension_Coil.csv` file, and place it in the active directory for your R session.
2. In your `MechaCarChallenge.RScript`, import and read in the `Suspension_Coil.csv` file as a table.
3. Write an RScript that creates a `total_summary` dataframe using the `summarize()` function to get the mean, median, variance, and standard deviation of the suspension coil’s PSI column.

Your `total_summary` dataframe should look like this:

![d1](https://github.com/emmanuelmartinezs/MechaCar_Statistical_Analysis/blob/main/Resources/Images/data-15-total-summary-data-mean-median-variance-sd.png)

4. Write an RScript that creates a `lot_summary` dataframe using the `group_by()` and the `summarize()` functions to group each manufacturing lot by the mean, median, variance, and standard deviation of the suspension coil’s PSI column.
Your lot_summary dataframe should look like this:

![d1](https://github.com/emmanuelmartinezs/MechaCar_Statistical_Analysis/blob/main/Resources/Images/data-15-manufacturing-lot.png)

5. Save your `MechaCarChallenge.RScript` file to your GitHub repository.

> To Deliver. 

You will earn a perfect score for Deliverable 2 by completing all requirements below:

- The Suspension_Coil.csv file is imported and read into a dataframe
- An RScript is written to create a total summary dataframe that has the mean, median, variance, and standard deviation of the PSI for all manufacturing lots
- An RScript is written to create a lot summary dataframe that has the mean, median, variance, and standard deviation for each manufacturing lot
- There is a summary that addresses the design specification requirement for all the manufacturing lots and each lot individually

The Suspension Coil dataset provided for the MechaCar contains the results of testing the weight capacities of multiple suspension coils from multiple production lots to determine consistency. 

First looking at all manufacturing lots:

![d2](https://github.com/Hanzian/MechaCar_Statistical_Analysis/blob/main/Pictures/Total%20summary.png)

Diving a little deeper into each of the 3 lots:

![d2](https://github.com/Hanzian/MechaCar_Statistical_Analysis/blob/main/Pictures/Lot%20summary.png)

With the understanding that the design specifications for the MechaCar suspension coils mandate that <mark style="background-color: Yellow">**the variance of the suspension coils cannot exceed 100 pounds per square inch (PSI)**</mark> . 

Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

When looking at the entire population of the production lot, the variance of the coils is 62.29 PSI, which is well within the 100 PSI variance requirement.  

Similarly, but significantly more consistent, Lot 1 and Lot 2 are well within the 100 PSI variance requirement; with variances of 0.98 and 7.47 respectively.  However, it is Lot 3 that is showing much larger variance in performance and consistency, with a variance of 170.29.  It is Lot 3 that is disproportionately causing the variance at the full lot level.  

This very simple boxplot illustrates the differences between the lots:

![d2](https://github.com/emmanuelmartinezs/MechaCar_Statistical_Analysis/blob/main/Resources/Images/boxplot2.png)

