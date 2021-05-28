# Chemotherapy Drug Trials

Observations:
1. There was a strong correlation, with r greater than .75, between mouse weight and the average tumor volume across all time points.
2. The drugs which got the most tests were Ramicane and Infubinol, and the drug with the least tests was Propriva.
3. There were no outlier tumor volumes for Ramicane, Infubinol, Ceftamin, and Capomulin.

This project attempts to answer the question: on average, which cancer drug is most effective at reducing tumor volumes, and what is the relation between mouse weight and the rate of success in reducing tumor volumes?

To run the code in the Jupyter Notebook file, simply press the right-pointing play button to the left of each code cell.

Here is the first dataframe, which I made from merging the two datasets together on Mouse ID. The data has not been altered in any other way:
![image](https://user-images.githubusercontent.com/73863977/119921146-7e6d4c80-bf3b-11eb-9a66-9d88c68f74c9.png)

In this assignment, I checked the original dataset for the total number of unique mouse IDs.
I then checked to see if any mice had multiple data entries for the same time point, using a groupby object, visualized with a count function.
I identified one mouse as having duplicate time points and eliminated all data corresponding with that mouse ID.

I used the cleaned dataset to compute means, medians, variances, standard deviations, and standard errors of the mean for all of the numeric data in each drug regimen.
I displayed these calculated results in a new dataframe.

I created a bar graph showing the total number of tests done for each drug regimen.
I did this twice, first using pandas' innate graphing capabilities, then using matplotlib.
I attempted to make the formatting as similar as possible between both graphs.

I created a pie plot to show the sex composition of all the test mice.
I did this twice, first using pandas' innate graphing capabilities, then using matplotlib.
I attempted to make the formatting as similar as possible between both plots.

I used .loc() to reduce my cleaned dataframe to only data for Capomulin, Ramicane, Infubinol, and Ceftamin, for only timepoints of value 45.
I made a datframe showing the quartiles and InterQuartile Range for the final tumor volumes for each of these 4 drugs.
To this dataframe, I added an "Outliers?" column containing "Yes" or "No" answers based on a calculation of whether maximum and minimum tumor volumes for each drug lay outside the bounds of Q1-1.5IQR and Q3+1.5IQR.


I used .loc() and .sample() on my cleaned DataFrame to eliminate all data not for Capomulin and then to select and print a random row.
I used the Mouse ID from the row returned by .sample() to .loc() the dataframe for only that Mouse ID and to make a line graph of that mouse's tumor volume over time.

I used matplotlib to generate a scatterplot of mouse weights vs. over-time averaged tumor volumes for all the mice treated with Capomulin.
I then used linregress() to get the slope and y-intercept of the linear regression model for this plot.
I drew the regression line on the plot and printed the slope and y-intercept for the model in a text statement.
In the same text statement, I reported the correlation coefficient for the scatterplot linear regression model.
