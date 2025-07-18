# Foreign Trade Analysis using Python


## Overview

This project presents a comprehensive analysis of import-export data sourced from a CSV file. The objective was to derive meaningful insights by performing end-to-end data processing and visualization. The key steps involved are data cleaning, data manipulation and data visualization.This project demonstrates the complete data analytics pipeline from raw data to actionable insights, showcasing data preprocessing, analysis, and storytelling through visuals.


## **Table of Contents** 
- [Imported Libraries](#imported-libraries)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Insights Generation](#insights-generation)
- [Techniques Used](#techniques-used)
- [Example](#Example)
- [Contributing](#contributing)
- [Contact](#contact)

## **Imported Libraries**

These are the python libraries i have imported for this project.

- pandas: used for creating, exploring and manipulating dataframes for data analysis
- numpy: used for numerical computations and array operations
- matplotlib: used for creating static plots
- seaborn: built in top of matplotlib for aesthetic pleasing visuals
- plotly: used for interactive and dynamic data visualization

## **Exploratory Data Analysis**

### **Creating and exploring HSCODE dataframe**

- This dataframe was created using the data from excel file named **'meidb-principal-Commoditywise-all-hscode-import.xlsx'**
- This file contains India's total import of Tea commodities and their corresponding hscode over the periods.
- This Dataframe contains 24 rows and 10 columns.
- Explored the dataframe using describe() function to get key statistical summaries of numerical columns, including mean, standard deviation, and percentiles, which helped identify outliers and trends.
- The info() function was used to check for null values, data types, and overall data completeness, aiding in decisions for further data cleaning and preprocessing.
- Checked wheather the dataframe contains duplicated values or not.
- I have created a copy of the dataframe using df.copy() as for not affecting the original dataframe while doing some data transformation.
- While exploring the dataset, I noticed uneven spacing and whitespaces in the column names. To ensure consistency and ease of access during analysis, I removed those extra whitespaces.

- Found 3 duplicate columns in dataframe with differnt column names. I checked each row of those columns to ensure that they are duplicate column using the code **" hscode1[hscode1['Apr-2024 (F)'] !=   hscode1['Apr-Apr2024 (F)']] "**. After ensuring that those 3 columns are just a copy of other columns, i dropped those duplicate column from the dataframe.
- Then exported the cleaned dataframe to a new csv file HSCODE.csv using pd.to_csv() function.

### **Creating and exploring top_contries_total_trade dataframe**

- This dataframe was created using the data from excel file named 'eidb-top-n-countries-totaltrade.xlsx'
- I have first created a sample dataframe by just importing 10 rows from the excel file to see the table structure and to find which row of the file contains header.
- I have created the original dataframe and performed the above mentioned data exploration methods for better understanding the data.
- Then **converted some numerical values which was originally in object datatype to float datatype** (which was quite tricky as it contained some symbols between those values and some null values are mentioned as '-' )

- Then exported the cleaned dataframe to a new csv file top_n_countries.csv using pd.to_csv() function

### **Creating and exploring commodity_group dataframe**

- This dataframe was created using the data from excel file named 'ftpa-Commodity Group-wise.xlsx'
- Used above mentioned exploration methods and also checked unique values of the dataframe.
- Changed the object datatype to float datatype for numerical columns.
- Checked the percentile values of a column to check outliers using **commodity_group.describe(percentiles = np.arange(0.75,1,0.02 )).round(2)**
- Then cleaned dataframe was exported to a new csv file

### **Creating and exploring commodity_wise_export dataframe**

- This dataframe was created using the data from excel file named 'ftspcc-commoditywise-export.xlsx'
- Used above mentioned exploration methods and also checked unique values of the dataframe.
- Changed the object datatype to float datatype for numerical columns.
- Exported the cleaned dataframe to a new csv file

### **Creating and exploring commodity_wise_import dataframe**

- This dataframe was created using the data from excel file named 'ftspcc-commoditywise-import.xlsx'
- Used above mentioned exploration methods and also checked unique values of the dataframe.
- Changed the object datatype to float datatype for numerical columns.
- Exported the cleaned dataframe to a new csv file
---
### **Creating and exploring country_wise_trade dataframe for 2024-2025**

- This dataframe was created using the data from excel file named 'ftspcc-countrywise-ttrade.xlsx'
- Used above mentioned exploration methods and also checked unique values of the dataframe.
- Created custom column names to add the year in front of column names.
- Changed the object datatype to float datatype for numerical columns.
- Exported the cleaned dataframe to a new csv file
---
### **Creating and exploring country_ttrade23_24 dataframe for 2023-2024**

- This dataframe was created using the data from excel file named 'ftspcc-countrywise-ttrade1.xlsx'
- Used above mentioned exploration methods and also checked unique values of the dataframe.
- Created custom column names to add the year in front of column names.
- Changed the object datatype to float datatype for numerical columns.
- Exported the cleaned dataframe to a new csv file

