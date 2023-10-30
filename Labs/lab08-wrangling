# Lab 8: Data Wrangling and Cleaning

### Setup and Submission - please read and follow carefully
* *Accept the Assignment*: When you accept the assignment in GitHub Classroom, a repository named `lab-08` will be automatically generated for you under the "s386Fall2023" organization.
* *Locate Your Repository*: Your personal repository for this homework can be found at `https://github.com/s386Fall2023/lab-08-your_user_name`.
* *Clone the Repository*: 
    - Open your terminal and navigate to the directory where you want to download the repository.
    - Run `git clone your_repository_URL` to clone the repository onto your local machine.
* *Create a `.gitignore file*:
    - Before committing your work, create a `.gitignore` file appropriate for this assignment.  
* *Working Directory*: The cloning process will create a new directory named `lab-08-your_user_name`. Ensure that you perform all your work inside this directory.
* *Commit Your Progress*: As you work on the assignment, remember to commit your changes periodically. You can easily do this using Visual Studio Code (VS Code).
* *Remote Connection*: If you've cloned the repository correctly and are working within the created directory, the remote link to your GitHub repository should already be configured.
* *Virtual Environment*: Ensure that you are using the class's virtual environment while working on this assignment.
   - Note:  There is no way to tell from your submission whether or not you use the class environment.  However, if you are working in the virtual environment set up for our class, then you can be sure that you are using the correct versions of the packages.
* *File and Function Names*:
    - Your repository should contain the following files:
        * This `Readme.md` file
        * `employee_clean.csv`
        * `clean_weather.csv`
        * `TB2022_clean.csv`
        * `uscities.csv`
        * `lab08_answers.txt`
        * A non-empty `.gitignore` file
        * A `.py` or `.ipynb` containing the neat and well-documented code you used to complete the assignment
* *Submission to Gradescope*:    
    - Once you've completed the assignment, go to Gradescope and select your personal homework repository (`https://github.com/s386Fall2023/lab-08-your_user_name`) as the source for your submission.


## Questions

Data for this Lab is found in the [MessyData folder](https://github.com/esnt/Data/tree/main/MessyData) of my [Data Repository](https://github.com/esnt/Data) on GitHub.  

Data can be loaded directly from GitHub into pandas by using the url to the "raw" file:
```
url = 'https://github.com/esnt/Data/raw/main/MessyData/employee.csv'
df = pd.read_csv(url)
```
If you are getting an error, you might be using the wrong url.  Make sure that you see the word "raw" somewhere in the url. 


## Question 1

Finish the cleaning activity that we started in class on October 24.

Clean the "`employee.csv`" file by completing the following tasks.  (Try using regular expressions for a few of the tasks to practice). 

* (a.) Extract the first and last names from the "`name`" column and create two new variable called "`first_name`" and "`last_name`"
* (b.) Extract the area code from the phone number column and create a new variable called "`area_code`"
* (c.) Extract the year from the "`birthdate`" column and create a new variable called "`birthyear`"
* (d.) Create a columns that is the height in inches
* (e.) Create a column that contains the domain of the email addresses (e.g. "`yahoo.com`")
* (f.) Create a variable that computes the age at the time of starting 
* (g.) Extract the city and state from the "`mailing_address`" and create three new variables called "`city`", "`state`", and "`zipcode`"
* (h.) Keep only the new variables that you created in parts (a.) - (g.)  You final dataset should look something like this:

| first_name | last_name | area_code | birthyear| ht_in| domain | age | city | state | zipcode |
|------------|-----------|-----------|----------|-------|-------|--------|-----|---------|------|
| Ryan | Wilkins | 851 | 1959 | 74 | hotmail.com | 47 | Port Victoria | MN | 71782

**Save the cleaned data in a file called "`employee_clean.csv`" and include it in this repository.**

---
## Question 2
The "`messy_weather.csv`" dataset contains information from a weather station 2006 - 2023.  The weather variables included are `TMAX` (maximum daily temperature), `TMIN` (minimum daily temperature), and `PRCP` (daily precipitation).  

Clean and tidy this dataset so that there is a row index that corresponds to the date and six other columns: `year`, `month`, `day`, `tmax`, `tmin`, and `prcp` (notice the variable names are in lowercase).  Your final dataset should look something like this (without the words in `()`):


|   | year | month | day | tmax | tmin | prcp |
|----------|-----|-----|-----|-----|-----|-----|
|   |  (int)   |  (int)   |  (int)   |   (float)  |   (float)  |  (float)   |  
|   (date)  |    |    |    |     |     |     | 
|   2006-01-01  |  2006  | 1   | 1   |  0.3   |  32.0    |  21.0   | 
|   2006-01-02  |   2006 | 1   |  2  |   2.1  |   36.0  |  26.0   | 
|   ...  |  ...  | ...   |  ...  |  ...   | ...    | ...    | 
|   2023-10-18  |  2023  |  10  |  18  |  0.0   | 63.0   |   42.0  | 

*More details about the cleaning:*
- Each row should correspond to a unique date
- If there are any replicate dates, the final dataset should be the mean values for the date
- Values 9999 are missing values and should be replaced with NaN (np.nan)
- There should be are no rows corresponding to nonsensical dates (e.g., April 31)
- Drop rows in which `tmax`, `tmin`, and `prcp` are all missing
- *Hint*:  You will need to use **both** `pivot` and `melt` 


**Save the cleaned data as `"clean_weather.csv"` and answer the following questions. Answers should be added to the "`lab08_answers.txt`" file.** 
    a. How many rows are there in the tidy dataset?  
    b. What is the overall mean of tmax (maximum daily temperature)?    
    c. What is the mean across years of tmin (minimum daily temperature) on August 1.    
    d. What date (month/day/year) has the largest prcp (daily precipitation)?  
    e. What is the value of the largest prcp?   
    f. Which month has the largest average difference between tmin and tmax?

---
## Quesion 3
The "`TB2022.csv`" contains data downloaded from the [WHO](https://www.who.int/teams/global-tuberculosis-programme/data) about the number of tuberculosis cases by country for the years 2012-2020.  

Tidy and clean the dataset.
- There should be seven columns when you are finished: `country`, `region`, `year`, `sex`, `age`, `cases_ffill`, and `cases_bwfill`
- ` region` is the same as `g_whoregion` 
- The age categories are 0-14, 15-19, 20-24, 25-34, 35-44, 45-54, 55-64, 65+
    - Ideally the values of your age variable correspond to the categories listed above, however, it's okay if you leave the values as 014, 1519, 2024, 2534, 3544, 4554, 5564, 65
- **Sort the data by country then year then sex then age.** Be sure to do the sort before doing the fill.  Fill missing cases using both the forward- and backward-fill methods
- **Save your cleaned data as "`TB2022_clean.csv`" and include it in this repository.**
- **Answer the following questions about the data. Answers should be added to the "`lab08_answers.txt`" file.**       
        a. Using the forward-fill method, what is the mean number of cases for females aged 55-64?    
        b. Using the backward-fill method, what is the mean number of cases for females aged 55-64?      
        c. What sex/age combination has the largest difference between the ffill and bfill methods?   
        d. What sex/age combination has the smallest difference between the ffill and bfill methods? 


---
## Question 4: US Cities

Use the US Cities data from [Wikipedia](https://en.wikipedia.org/wiki/List_of_United_States_cities_by_population) that we used in Lab 5.  The following code will read the data into pandas for you:
```
import pandas as pd
url = 'https://en.wikipedia.org/wiki/List_of_United_States_cities_by_population'
tables = pd.read_html(url)
df = tables[4]
``` 
Create a cleaned dataset that has 7 columns.  The table below shows the column names and variable types that each column should have.

| city | state | population | land_area | pop_density | longitude | latitude |
|----------|-----|-----|-----|-----|-----|-----|
|   (object)  |  (object)   |  (int)   |  (float)   |   (float)  |   (float)  |  (float)   |     
   

* "`city`" and "`state`" should have all footnote references removed (e.g. `[d]`) 
* "`population`" should be the 2020 census value
* "`land_area`" should be land area in square feet
* "`pop_density`" should be population per square foot
* "`longitude`" should be the longitude in decimal form 
* "`latitude`" should be the latitude in decimal form

**Save the cleaned data in your repository as `uscities.csv`.**

**Remarks about latitude and longitude:**
* Latitude and longitude (lat/lon) coordinates can be measured using either decimal degrees OR degrees/minutes/seconds. The table that you read in from Wikipedia contains the lat/lon coordinates in both of these units. 
    * For example, in the string `34°01′N 118°25′W / 34.02°N 118.41°W` the coordinates before the `/` are in degrees and minutes and the coordinates after the `/` are in decimal degrees.  We want to extract the set of numbers after the `/`
* "North" coordinates correspond to latitude and "West" coordinates correspond to longitude
* The "`location`" coordinate of the first row might look like this when you examine the data:
    
    ```.mw-parser-output .geo-default,.mw-parser-output .geo-dms,.mw-parser-output .geo-dec{display:inline}.mw-parser-output .geo-nondefault,.mw-parser-output .geo-multi-punct,.mw-parser-output .geo-inline-hidden{display:none}.mw-parser-output .longitude,.mw-parser-output .latitude{white-space:nowrap}40°40′N 73°56′W\ufeff / \ufeff40.66°N 73.94°W```

    Even though it looks weird, it still contains the information that you need. 


