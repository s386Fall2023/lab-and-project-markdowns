---
title: "Lab 5: More Pandas"
layout: single
author_profile: false
classes: wide
excerpt: pandas practice
---

### Instructions
* *Accept the Assignment*: When you accept the assignment in GitHub Classroom, a repository named `lab-05` will be automatically generated for you under the "s386Fall2023" organization.
* *Locate Your Repository*: Your personal repository for this homework can be found at `https://github.com/s386Fall2023/lab-05-your_user_name`.
* *Clone the Repository*: 
    - Open your terminal and navigate to the directory where you want to download the repository.
    - Run `git clone your_repository_URL` to clone the repository onto your local machine.
* *Working Directory*: The cloning process will create a new directory named `lab-05-your_user_name`. Ensure that you perform all your work inside this directory.
* *Commit Your Progress*: As you work on the assignment, remember to commit your changes periodically. You can easily do this using Visual Studio Code (VS Code).
* *Remote Connection*: If you've cloned the repository correctly and are working within the created directory, the remote link to your GitHub repository should already be configured.
* *File and Function Names*: 
    - The answers to all the questions should be in the `answers.txt` file.  You will most likely edit the file manually (replace the `XXX` with your answer) 
      * ONLY replace the `XXX`.  Do not add any lines, delete or change problem numbers, or change the file name.
      * Do NOT round decimal numbers (all `float` answers should have AT LEAST 4 decimals)
    - Include your code in the file called lab_05_code.py.  Your code file should run without error and **print** all the answers to the questions. 
    - The answers you print in your code do not need to be *"exact."* For instance, when responding to Question 1, which asks "How many instances are in the dataset?", you have the option to use the `.info()` method or the `.shape` attribute (among other options) to obtain the answer. The key point is that the answer to the question can be derived from the results of these methods or attributes, even if they contain additional information.  
    - Read in the dataset using the GitHub urls (not as downloaded files)
* *Virtual Environment*: Ensure that you are using the class's virtual environment while working on this assignment.
   - Note:  There is no way to tell from your submission whether or not you use the class environment.  However, if you are working in the virtual environment set up for our class, then you can be sure that you are using the correct versions of the packages.
* *Submitting on Gradescope*: 
    - Once you've completed the assignment, go to Gradescope and select your personal homework repository (`https://github.com/s386Fall2023/lab-05-your_user_name`) as the source for your submission.
    - Ensure that the following files are in your repo: `answers.txt`, `avg_carrier_age.csv` (created in #13) and  `lab_05_code.py` 
    
-----

## Part 1:  Flights Data 

The data for part can be found in the [homework-data repository](https://github.com/esnt/Data).  

In the **Flights** directory there are several datasets containing information about fights
departing from the New York City area during the year 2013.  Origin airports included are LaGuardia Airport (LGA), John F. Kennedy International Airport (JFK) and Newark Liberty International Airport (EWR).  See the file *data-info.md* or *data-info.pdf* for information about the variables
in each of the datasets.   

Answer the questions below. 

#### Questions 1 - 10, will only use the *flights.csv* dataset
1.  How many instances (observations) are in the dataset?
2.  Missing values questions:
      * a. Which two variables have the most missing values?
      * b. How many missing values are there for these variables?
3.  What is the average (non-missing) `air_time` for the flights in the dataset?  
4.  How many unique `dest` values (destinations) are in the dataset?  
5.  What are the five most common destinations for the flights in the dataset (in order)?
      * a. (most common)
      * b.
      * c.
      * d.
      * e. (fifth most common)
6.  What is the maximum `distance` (in miles) flown in the dataset? 
7.  How many flights in the dataset flew the maximum `distance`?  
8.  Create a variable that indicates whether or not a flight was cancelled based on whether or not the `air_time` variable is missing. 
      * a. What **month** has the highest proportion of cancelled flights? (Use the two digit month number - for example, if the answer is January, use "01" in the answer file)
      * b. What is the proportion from (a.)?
      * c. What **origin** has the lowest proportion of cancelled flights? 
      * d. What is the proportion from (c.)?
9.  Arrival delay questions:
      * a. Which date has the largest average arrival delay (`arr_delay`)?   (Use the format MM/DD - for example, if the answer is Jan 9, use "01/09" in the answer file)
      * b. What is the average from (a.) in minutes?
10.  Each plane in the dataset has a unique `tailnum`.  
      * a. What is the `tailnum` of the most common plane in the dataset? 
      * b. How many times is the plane from (a.) in the dataset? 
      * c. What is the average `distance` that the plane from (a.) traveled (in miles)?  
      * d. What is the most common route (origin to destination) traveled for the plane from (a.)? (Use the format "ORG-DST", for example "JFK-SLC")

#### Questions 11-16 will use one or more other datasets in the *Flights* folder, including possibly `flights.csv`

{:start="11"}
11. How many planes have a missing year of manufacture?
12. 
      * a. Of the planes in the *flights*, what is the tail number of the oldest plane?
      * b. How old was the plane from part (a) in 2013 in years?
13. Create a DataFrame with 3 columns:  "carrier_name", "carrier", "avg_plane_age".  
      * "carrier_name" is the name of the carrier (i.e., "Delta Air Lines Inc.")
      * "carrier" is the two letter carrier abbreviation (i.e., "DL")
      * "avg_plane_age" is the average age of the planes in the *flights* data by carrier
      * Sort your the DataFrame by "avg_plane_age" so that the airline with the youngest average plane age is listed first.  
      * Ensure the index goes from 0-15 after you've sorted
      * Save the final DataFrame as csv file called "avg_carrier_age.csv" and include `index=None` so the index column is not saved as part of the csv
      * **COMMENT OUT the command to save the DataFrame before you submit your assignment so it is not re-saved if I run your code**
      * Include the `avg_carrier_age.csv` in your GitHub repository
      * **On the answers.txt file, report the `carrier_name` with the youngest average plane age** 
14. What is the correlation coefficient between the number of seats on a plane and the average distance it traveled?
15. How many *days* had precipitation in the New York area in 2013? (That is, how many **days** had non-zero precipitation at <u> at least one of the airports</u> in the dataset during <u>at least one of the hours</u>.)
16. Using only days with precipitation greater than zero, what is the correlation between precipitation and average minutes of departure delay?

## Part 2:  Practice with `pd.read_html`
There are 333 cities with a population of at least 100,000 as of July 1, 2022.  Information on these cities can be found here: [List of United States Cities by Population.](https://en.wikipedia.org/wiki/List_of_United_States_cities_by_population). 
* Use the pandas function `read_html` to scrape the tables from this webpage.  Remember that this function will return a list of all the tables from the page. 
   ```python
   tables = pd.read_html(url)
   ``` 
* Look through the list to find the table index which contains columns for population, area, and location. For instance, if the desired table is the third one on the page, its index would be 2 (since Python indexing starts at 0).
* Once you've identified the correct index, create a DataFrame from that table:
   ```python
   df = tables[index]
   ```
   (replace `index` with the correct number)
* Answer the questions below

{:start="17"}
17. How many tables are on this webpage?
18. What is the index of the table of interest?
19. According to the 2020 census, the population of the United States in 2020 was 331,449,281. What percentage of the population lives in one of the cities in the dataset? Use the 2020 census value rather than the 2022 estimate.
* Report the percentage as a decimal between 0 and 1
20. Various sources, including ChatGPT, indicate that the area of the United States (including Alaska and Hawaii) is approximately 3.8 million square miles. Using 3,800,000 as the area value, what percent of the US land is represented by the cities in the dataset? (Assume no overlap in the reported areas of the cities.)
* Report the percentage as a decimal between 0 and 1
