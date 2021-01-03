# Exploring Relationships in Body Dimensions : Project Overview

Peformed linear regression from scratch using the least squared formula. 

Create two linear regression models and their correlation: between a person's BMI (Body Mass Index) and their age, and between a person's weight and a combination of physical attributes (CPA). 

## Code and Resources used
* **Editor used** : Google Colaboratory
* **Packages used** : pandas, matplotlib, numpy, math

## About the Dataset

This dataset contains 21 body dimension measurements as well as age, weight, height, and gender on 507 individuals. The 247 men and 260 women were primarily individuals in their twenties and thirties, with a scattering of older men and women, all exercising several hours a week.

### Data Source:

Measurements were initially taken by the first two authors - Grete Heinz and Louis J. Peterson - at San Jose State University and at the U.S. Naval Postgraduate School in Monterey, California. Later, measurements were taken at dozens of California health and fitness clubs by technicians under the supervision of one of these authors.
Dataset Link : http://jse.amstat.org/jse_data_archive.htm

### Data Columns:

**Skeletal Measurements:**

* Biacromial diameter  
* Biiliac diameter, or "pelvic breadth" 
* Bitrochanteric diameter
* Chest depth between spine and sternum at nipple level, mid-expiration
* Chest diameter at nipple level, mid-expiration
* Elbow diameter, sum of two elbows
* Wrist diameter, sum of two wrists
* Knee diameter, sum of two knees
* Ankle diameter, sum of two ankles

**Girth Measurements:**

* Shoulder girth over deltoid muscles
* Chest girth, nipple line in males and just above breast tissue in females, mid-expiration
* Waist girth, narrowest part of torso below the rib cage,average of contracted and relaxed position
* Navel (or "Abdominal") girth at umbilicus and iliac crest, iliac crest as a landmark
* Hip girth at level of bitrochanteric diameter
* Thigh girth below gluteal fold, average of right and left girths
Bicep girth, flexed, average of right and left girths
Forearm girth, extended, palm up, average of right and left girths
Knee girth over patella, slightly flexed position, average of right and left girths
Calf maximum girth, average of right and left girths
Ankle minimum girth, average of right and left girths
Wrist minimum girth, average of right and left girths

**Other Measurements:**

* Age (years)
* Weight (kg)
* Height (cm)
* Gender (1 - male, 0 - female)

The first 21 variables are all measured in centimeters (cm).

There are no missing values.

## Tasks performed

1. Calculate the Body Mass Index (BMI).
> BMI= weight/(height) Note: weight in kg and height in meters 

2. Calculate the Combination of Physical Attributes (CPA). 
> CPA = -110 + 1.34(ChestDiameter) + 1.54(ChestDepth) + 1.20(Bitrochanteric Diameter) + 1.11(WristGirth) + 1.15(AnkleGirth) + 0.177(Height)

3. Regression and Correlation

Linear regression is a form of regression analysis in which the relationship between one or more independent variables and another variable, called the dependent variable, is modeled by a least squares function, called a linear regression equation. A linear regression equation with one independent variable represents a straight line when the predicted value (i.e. the dependant variable from the regression equation) is plotted against the independent variable: this is called a simple linear regression. 

The method we are going to use is called the least squares method. It takes a list of x values and y values (the same number of each) and calculates the slope and intercept of a line that best matches those values.

To calculate the least squares line, we need to calculate the following values from the data: 

* sumX and sumy: the sum of all the X values and the sum of all the Y values 
* sumXY: the sum of all the products of each corresponding X,Y pair
* sumXSquared and sumySquared: the sum of the square of every X value and the sum of the square of every Y value
* N: the number of pairs 

The calculation then is: 
> slope=(N * sumXY - (sumX * sumy))/(N * sumXSquared - (sumx)^2) 
> intercept = (sumy - (slope * sumx))/N 

We will also then calculate the correlation coefficient, and indication of how “linear” the points are (how much, in total, the points are correlated as a line). 

That calculation is: 

> corr = (N * sumXY - (sumX * sumy)) / sqrt((N * sumXSq - (sumx)^2) * (N * sumySq - (sumy)^2)) 

The correlation value ranges between-1 and 1. A negative value means an inverse correlation, a positive value a positive correlation. Values near - 1 or 1 are “good” correlations, values near 0 are "bad" correlations.

4. Plot the individual entries using matplotlib for both measures and the calculated regression lines through the data.
