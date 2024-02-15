Data Visualization Task
Task Description
The purpose of this task is to create a bar chart or histogram to visualize the distribution of a categorical or continuous variable. In this example, we will demonstrate how to create a bar chart to visualize the population distribution of a chosen country over the years.

Code Overview
The provided code utilizes the Python programming language along with the pandas and matplotlib libraries for data manipulation and visualization.

Dependencies
Make sure you have the following libraries installed:

bash

pip install pandas matplotlib
Code Explanation
Filtering and Converting Years to Integers:

Extracts the column names starting from the third column (index 2) because indexing starts from 0.
Filters out only those column names that consist of numeric characters (representing years).
Converts the filtered column names to integers.

years = country_data.columns[2:][country_data.columns[2:].str.isnumeric()].astype(int)
Extracting Population Data for the Corresponding Years:

Extracts the population data for the specified country for the years with numeric column names.
Converts the filtered population data to integers.

population = country_data.iloc[0, 2:][country_data.columns[2:].str.isnumeric()].astype(int)
Plotting the Data:

Creates a bar plot with years on the x-axis and corresponding population on the y-axis.
Sets labels for the x and y-axes, and a title for the plot.
Displays the plot.
plt.figure(figsize=(10, 6))
plt.bar(years, population, color='skyblue')
plt.xlabel('Year')
plt.ylabel('Population')
plt.title(f'Population of {chosen_country} Over the Years')
plt.show()
