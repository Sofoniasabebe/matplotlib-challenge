# matplotlib-challenge
### Generating tables and figures needed for the technical report of the clinical study and  a top-level summary of the study results using Matplotlib. 
The following were the tasks identified for this challenge:
* Preparing the data.
* Generating summary statistics.
* Creating bar charts and pie charts.
* Calculating quartiles, finding outliers, and creating a box plot.
* Creating a line plot and a scatter plot.
* Calculating correlation and regression. 
A final analysis was also provided in the beginning of the notebook.

There were three dependencies provided in the starter code. I had to add a couple more dependencies as I continued with the challenge. I found importing numpy and linregress from the scipy.stats valuable to the project.

Although the file paths for the challenge were provided in the starter code, I had to make minor adjustments as I had created a directory for the data and another directory for the main script to run from.

I then combined the two data sets into a single DataFrame using pd.merge() on the 'Mouse ID' column. I reordered the columns to resemble the DataFrame in the starter code.

Using the .unique() method, I was able to count the number of unique mice in the 'Mouse ID' column; there were a total of 249 mice.
I used a combination of .duplicated() and .unique() methods to identify the duplicate mice. There was a total of 13 duplicate IDs identified. I then created a clean DataFrame by dropping the duplicates. A count was performed afterwards and the number of mice in the cleaned DataFrame came to be 248.

The next step was to create a DataFrame of summary statistics. I recognized the availability of more than one way to produce the results and chose to use the .agg() method for simplicity. Accordingly, a summary statistics table of mean, median, variance, standard deviation, and SEM of the tumor volume for each regimen was created.

Bar plot was generated using the DataFrame.plot() method and pyplot methods. Both approaches generated identical bar charts. Similarly, two pie charts were created using the DataFrame.plot() method and pyplot methods.

I then calculated the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Then, I calculated the quartiles and IQR, and determined if there were any potential outliers across all four treatment regimens.

Using Matplotlib, I generated a box plot that shows the distribution of the final tumor volume for all the mice in each treatment group. I also highlighted an outlier in the plot by changing the color and style.

I selected a single mouse that was treated with Capomulin, and generated a line plot of tumor volume versus time point for that mouse.

I also generated a scatter plot of mouse weight versus average observed tumor volume for the entire Capomulin treatment regimen.
Then, the correlation coefficient and linear regression model between mouse weight and average observed tumor volume for the entire Capomulin treatment regimen were generated. The linear regression model was plotted on top of the previous scatter plot.

## Analysis

* The first visualized output of the analysis is the bar chart that shows the number of observed mouse time points. The graph shows that two regimens have the highest numbers; the regimens are Capamulin and Ramicane. Both regimens have observed time points exceeding 200.
* As depicted in the pie charts, there appears to be a balanced gender distribution; the split is nearly equal with 50.4% male and 49.6% female.
* The visualization of the distribution of tumor volume for the four selected regimens in the box plot provided some insight into the effectiveness of Capomulin and Ramicane. Both regimens appear to have lowered tumor volumes than the remaining two regimens, thereby indicating their effectiveness. The box for Capomulin is notably smaller indicating that there is less variability in the data. Put differently, the IQRs indicate smaller variability. Infubinol and Ceftamin, on the other hand, showed wider IQRs indicating more variability in the outcome of the treatments. It is safe to say that the two regimens performed poorly in reducing tumor volume. One noticeable outcome of the box plot is that it showed an outlier in the Infubinol regimen indicating the presence of a mouse with significantly smaller tumor volume (mm3) than others in the group.
* The mouse selected for the line plot, L509, showed the effectiveness of the Capomulin regimen. Although an initial steady increase in tumor volume was seen for about 20 days, the volume significantly decreased. With a couple of stabilizations and slight increases, the line plot certainly depicts the effectiveness of the regimen in lowering tumor volume. This single mouse analysis corroborates the previous positive assessment of the Capomulin regimen.
* The scatter plots reveal a positive correlation between mouse weight and average tumor volume. As the weight of the mice increases, the tumor volume also tends to rise. This positive relationship is further confirmed by the correlation coefficient of 0.84.

