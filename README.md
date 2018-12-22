# College Data ETL Project

The purpose of this project is to demostrate an ETL pipeline to pull college data from multiple CSV files and combine them into one in order to analyze the rate of return on different college educations.

## The Data:
The data chosen was pulled from multiple sources.  The initial three CSV files were pulled from Kaggle.com and data.world.com. The dataset that was used to help in the cleaning was pulled from collegescorecard.ed.gov.  All the CSV files can be found in the repository except for the college scorecard data.  The file was to large to upload.  To retrieve the data, go to the last link and download the file from the link named "Most Recent Data".
### Data Links:
https://www.kaggle.com/wsj/college-salaries#degrees-that-pay-back.csv  
https://www.kaggle.com/smithashivakumar/college  
https://data.world/education/university-rankings-2017  
https://collegescorecard.ed.gov/data/  

## Extract
For the extract portion of the pipeline we used the pandas library in python to pull in the data from the CSV.  We chose this method because the pandas library makes manipulating data tables very easy.  Once all the data was pulled into python we could start to cleanup and transform it.

## Transform
The transform section was performed in the following steps:
1. Remove unnecessary columns from the dataframes
2. Create a column in each dataframe that has the school name in lower case with all the spaces and special characters removed
3. Merge the dataframes together using left join on the merge_name column created in step 2.
4. Using the college scorecard data to fill in missing values for Acceptance Rate and Starting Salary.

## Load
The final dataframe was stored as a CSV file.  This was chosen so anyone can use the transformed data later for statistical and visual analysis.


## Challenges
One challege of this project was trying to merge the tables together.  All the tables had slight variations of the school names that would cause issue with merging.  This was overcome by creating a merge_name column where the names where converted into easier to merge strings.
The other challenge involved missing data between the initial three files.  After the first merge over half the schools were missing acceptance rate and starting salary data.  In order to remedy this situation, another data file was imported from college scorecard.  Using the new data roughly 75% of the data was recovered.
