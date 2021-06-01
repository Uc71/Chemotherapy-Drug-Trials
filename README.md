# Chemotherapy Drug Trials

Observations:
1. There was a strong correlation, with r greater than .75, between mouse weight and the average tumor volume across all time points.
2. The drugs which got the most tests were Ramicane and Infubinol, and the drug with the least tests was Propriva.
3. There were no outlier tumor volumes for Ramicane, Infubinol, Ceftamin, and Capomulin.

This project attempts to answer the question: on average, which cancer drug is most effective at reducing tumor volumes, and what is the relation between mouse weight and the rate of success in reducing tumor volumes?

To run the code in the Jupyter Notebook file, simply press the right-pointing play button to the left of each code cell.

Here is the first dataframe, which I made from merging the two datasets together on Mouse ID. The data has not been altered in any other way:
![image](https://user-images.githubusercontent.com/73863977/119922797-91cde700-bf3e-11eb-9482-b0a1b1831a3b.png)

In this assignment, I checked the original dataset for the total number of unique mouse IDs.
I then checked to see if any mice had multiple data entries for the same time point, using a groupby object visualized with a count function.
I identified one mouse as having duplicate time points and eliminated all data corresponding to that mouse ID.
Here is data for the duplicated mouse:
![image](https://user-images.githubusercontent.com/73863977/119921332-ce4c1380-bf3b-11eb-9530-f31312904503.png)
Here is the cleaned dataframe:
![image](https://user-images.githubusercontent.com/73863977/119921432-fcc9ee80-bf3b-11eb-9cdb-417b2da7bb78.png)


I used the cleaned dataset to compute means, medians, variances, standard deviations, and standard errors of the mean for all of the numeric data in each drug regimen.
I computed each statistic as a new dataframe and then merged all the dataframes into one df, pictured here:
![image](https://user-images.githubusercontent.com/73863977/119921483-14a17280-bf3c-11eb-9053-4f380790d83c.png)
Then, I accomplished the same task again, using the aggregation method to compute all the stats in one line of code. The result is here:
![image](https://user-images.githubusercontent.com/73863977/119921987-eec89d80-bf3c-11eb-9209-5d5561033e7b.png)



I created a bar graph showing the total number of tests done for each drug regimen.
I did this twice, first using pandas' innate graphing capabilities, then by using matplotlib.
I attempted to make the formatting as similar as possible between both graphs.
The pyplot chart is here:
![image](https://user-images.githubusercontent.com/73863977/119922062-0e5fc600-bf3d-11eb-9db2-027ea41ef983.png)

The matplotlib chart is here:
![image](https://user-images.githubusercontent.com/73863977/119922097-220b2c80-bf3d-11eb-9af7-534ef0474c32.png)


I created a pie plot to show the sex composition of all the test mice.
I did this twice, first using pandas' innate graphing capabilities, then using matplotlib.
I attempted to make the formatting as similar as possible between both plots.
The pylot chart is here:
![image](https://user-images.githubusercontent.com/73863977/119922176-4bc45380-bf3d-11eb-8136-6d11f7395df0.png)


The matplotlib chart is here:
![image](https://user-images.githubusercontent.com/73863977/119922193-57b01580-bf3d-11eb-88db-d46fad377b40.png)



I used .loc() to reduce my cleaned dataframe to only data for Capomulin, Ramicane, Infubinol, and Ceftamin, for only timepoints of value 45.
Here is the df with only the 4 drugs of interest at timepoint=45:
![image](https://user-images.githubusercontent.com/73863977/119922270-7a422e80-bf3d-11eb-8dde-a5572b4b1d7c.png)


I made a dataframe showing the quartiles and InterQuartile Ranges of the final tumor volumes for each of these 4 drugs.
To this dataframe, I added an "Outliers?" column containing "Yes" or "No" answers based on a calculation of whether maximum and minimum tumor volumes for each drug lay outside the bounds of Q1-1.5IQR and Q3+1.5IQR. Here is the result:
![image](https://user-images.githubusercontent.com/73863977/119922292-8af2a480-bf3d-11eb-9c29-0ebe141454d9.png)


Here is a box plot of the final tumor volume for each drug:
![image](https://user-images.githubusercontent.com/73863977/119922416-c1c8ba80-bf3d-11eb-874a-8547e41c5484.png)


I used .loc() and .sample() on my cleaned DataFrame to eliminate all data not for Capomulin and then to select and print a random row.
I used the Mouse ID from the row returned by .sample() to .loc() the dataframe for only that Mouse ID and to make a line graph of that mouse's tumor volume over time:
![image](https://user-images.githubusercontent.com/73863977/119922488-e1f87980-bf3d-11eb-83b5-04de2b20c7ba.png)


I used matplotlib to generate a scatterplot of mouse weights vs. averaged-over-time tumor volumes for all the mice treated with Capomulin.
I then used linregress() to get the slope and y-intercept of the linear regression model for this plot.
I drew the regression line on the plot and printed the slope and y-intercept for the model in a text statement.
In the same text statement, I reported the correlation coefficient for the scatterplot linear regression model.
![image](https://user-images.githubusercontent.com/73863977/119922538-fdfc1b00-bf3d-11eb-986b-38f8c494e84d.png)
![image](https://user-images.githubusercontent.com/73863977/119922554-081e1980-bf3e-11eb-8099-74b8e77c8fb4.png)

