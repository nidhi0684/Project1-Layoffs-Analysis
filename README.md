# Project 1 - Layoffs Data Analysis Post Covid-19
## Project Intro
In this project, I conducted an extensive analysis of global layoffs since the onset of the pandemic in 2020. Leveraging a comprehensive dataset, I explored various trends in layoffs both on a global scale and within specific industries. To bring this analysis to life, I harnessed the power of Python visualization libraries and the Geoapify API, enabling me to create compelling visual representations of the data.

![image info](./Output_Data/Images/GeoView_Countries.png)

## Instructions
This project is broken down into two deliverables Layoffs_Dataset_Cleanup and Layoffs_Dataset_Analysis.

### Prerequisties and Assumptions
-  This project is developed on Jupyter Notebook version 6.5.4
- Following Python libraries are required to run both part of the project
   - numpy 
   -  pandas 
   - requests
   -  json
   -  time
   - matplotlib.pyplot
   -  hvplot.pandas
   - geopandas  
- 

### Part 1: Dataset Cleanup
I got my project's data from [Kaggle](https://www.kaggle.com/), I downloaded the Layoffs Dataset from the website.
1. I then massaged the data to check and remove unwanted records and clean the data for further analysis.
2. Added two new columns for latitude and longitude to be used for Geoviews
2. Next, the [Geoapify API](https://www.geoapify.com/) and the [geoViews Python library](https://geoviews.org/) is used to retrieve respective cities latitude and longitude coordinates data for each city.
3. A clean sanitized dataset is then stored in the Output_Data folder to be used for further analysis in the next phase.

### Part 2: Dataset Analysis
This part of the projects focuses on using the sanitized dataset to analyze layoffs data since Covid-19. I have asked a set of questions to my sanitized data set and used various visualizations methods to efficently read the results.
1. What are the top 10 countries affected by layoffs?
   - Percentage of layoffs for top 10 countries.
   - Total number of layoffs in top 10 countries.
2. What are the top 10 industries affected by layoffs?
   - Percentage of top 10 industries affected by layoffs.
   - Total number of layoffs in top 10 industries.
3. What are the top 10 company stages that are affected by layoffs?
   - Total number of layoffs across different company stages.
4. What is the time series analysis of layoffs since Covid-19?
   - Worldwide layoffs count since Covid-19
   - USA vs ROW (Rest of the World) layoffs count since Covid-19
5. What is the relation between US vs ROW data?
   - Top 5 Cities
   - Top 5 Industries 
   - Top 5 Companies
6. What is the per year layoff statistics for USA since Covid-19?
   - By Industry
   - By Companies
7. What is the per year layoff statistics for Rest of the world (ROW) since Covid-19?
   - By Industry
   - By Companies
8. Boxplot and whisker plot for top 5 USA industries.
9. What is the impact of layoffs throughout the world?
   - World cities impacted
   - Countries impacted

## How to execute code?
1. Open api_keys.py under resources folder located at the same location as these jupyter notebooks.
2. Assign your Geoapify API key to "geoapify_key" variable.
3. Run `Layoffs_Dataset_Cleanup.ipynb` to read and clean the dataset before analysis 
**API keys will be required for Geoapify**.
5. `Layoffs_Dataset_Analysis.ipynb` should be run next as it is dependent on the data massaged in step 4. 
7. Graphs created by `Layoffs_Dataset_Analysis.ipynb` will be stored in `Output_Data\Images`.

## Specific Analysis for each of questions asked to the dataset 
- #### What are the top 10 countries affected by layoffs?
   -  The top 10 results from the dataset show that United States is most affected by layoffs (70.2%) compared to the other countries.
   - China is the least affected with only 1.3%.
- #### What are the top 10 industries affected by layoffs?
   - Analysis of the top 10 rows of the dataset indicates that retail segment is most affected by layoffs. The layoff percentage in retail is 15.8%.
   - Consumer segment is very close at 15.4%.
   - Real Estate is the least impacted of all the other industries at 5.1%.

- #### What are the top 10 company stages that are affected by layoffs?
   - Public listed companies are most affected by layoffs.
   - Other stages before IPO have very minimal impact from layoffs.

- #### What is the time series analysis of layoffs since Covid-19 worldwide and USA vs Rest of the World (ROW)?
   - Based on the yearly layoff counts over the last 4 years across the world (USA and Rest of the world) we can say that the layoffs increased at the start of pandemic but gradually stabilized as the industries got used to the new way of functioning.
   - However, we can evidently see in the line graph that as the pandemic ended we see an evident increase in the layoffs count across the globe. This can be attributed to overhiring during the time of pandemic in certain business segments to meet the growing demands of customers.

- #### What is the relation between US vs ROW data? In terms of 1. Cities, 2. Industries and 3. Companies. Note: Only top 5 records chosen for analysis
   - In USA Cities, SF bay area was most hit by layoffs and in ROW it was Bengaluru in India
   - In USA Consumer industry was most affected by layoffs, however for ROW food industry saw the most layoffs.
   - In USA Amazon did the most number of layoffs, since Covid-19. In rest of the world it was Philips 

- #### What is the per year layoff statistics for USA since Covid-19 in terms of Industries and Companies?
   - The stacked bar chart to show the year over year analysis of layoffs in various industries across USA show that Consumer industry is most impacted followed by retail and others as the top 3 industries.
   - The stacked bar chart to show the year over year analysis of layoffs in various companies across USA show that Amazon's headcount for layoffs is the highest since Covid -19 followed by Meta and Google as the top 3 companies as per the layoffs count.

- #### What is the per year layoff statistics for ROW since Covid-19 in terms of Industries and Companies?
   - The stacked bar chart to show the year over year analysis of layoffs in various industries across ROW show that Food industry is most impacted followed by Finance and others as the top 3 industries.
   - The stacked bar chart to show the year over year analysis of layoffs in various companies across ROW show that Philips's headcount for layoffs is the highest since Covid -19 followed by Ericsson and Flink as the top 3 companies as per the layoffs count.

- #### Boxplot and whisker plot for top 5 USA industries
   - From Box and Whisker plot, it can be inferred that majority of the companies that fall in Consumer & Retail industries on an average laid off approximately equal number of workforce. While companies in Hardware industry had unequal numbers of the laid off workforce. This can be seen from the variance between first and third quartile for the Hardware industry.

- #### What is the impact of layoffs throughout the world? Cities and Countries
   - Please refer to the first geo map that highlights the cities impacted throughout the world by layoffs since Covid-19.
   - The second geo map shows the layoffs across the different countries based on the layoffs count. The color scale varies from dark to light shades based on the total layoffs count generating a heat map for it.

## Overall Conclusion from the Data Analysis
- Impact of Covid-19 has been across the world.
- Top industries impacted were Consumer, Retail, Transportation.
- Surprisingly, Public companies are impacted more than privately funded companies. This could be because of the external pressure of shareholders on public companies which led to operational cost reduction.
- Though companies like Google, Meta are Tech companies they are categorized as consumer industry in this dataset because of their product offerings are consumer focused.
- With start of Covid-19, there were specific industries like Transportation, Hospitality, Retail that got impacted immediately. However, with rise in digital work environment Tech companies over-hired during pandemic to support this growth. Post-pandemic (late 2022 and 2023), these companies and industries did most layoffs to balance for over hiring during pandemic.

## Future Enhancements
- I want to combine this dataset with the H-1B immigration status dataset to study the effects of layoffs on non immigrants in the USA

## Abbreviations
   - ROW: Rest of the World

## References
- **Geoapify API** https://www.geoapify.com/
- **geoViews Python Library** https://geoviews.org/
- **Kaggle** https://www.kaggle.com/
- **Matplotlib Documentation** https://matplotlib.org/stable/index.html

