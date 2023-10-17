---
title: "Lab 6: APIs and Web scraping"
layout: single
author_profile: false
classes: wide
excerpt: Practice working with APIs and collecting data through scraping and parsing html.
---

## Part 1: Exchange Rates API

For this part, use the [Exchange Rates API](https://apilayer.com/marketplace/exchangerates_data-api).  If you didn't sign up for an API key in class, then follow the steps below to sign up for your key:
* Go to [https://apilayer.com/marketplace/exchangerates_data-api](https://apilayer.com/marketplace/exchangerates_data-api)
* You'll have to verify your email address and sign in
* If you are taken back to the main page, search for "exchange rates" and click on "Exchange Rates Data API"
* Under Pricing, find "Free Plan" and click "Subscribe"
* If everything went well, you should then see a screen that says "Subscription successful" and "Your API Key"
* Copy your API key to the clipboard and then save it in a .txt file (choose a sensible name for the file like "`exchange_rates_apikey.txt`")
* **NEVER NEVER NEVER post your API key in a public place.  Anytime you use Git or GitHub with any API key, include the file with the key information in the `.gitignore` file**


A. Use the `/symbols` endpoint to find the currency name of the following three-letter currency codes:
* MXN
* BRL
* HUF
* KRW
* ZAR
* NZD
* AED
* USD

Once you have the results of the endpoint, you could set up a loop to find the right currency name.  For example
```python
codes = ['MXN', 'BRL', 'HUF', 'KRW', 'ZAR', 'NZD', 'AED', 'USD']

# pseudo-code below
for code in codes:
    if (some condition that looks for code):
        print(currency name)
```

B. Use `/timeseries`  endpoint to find the exchange rates for the eight currencies in (1) as compared to the Euro (EUR) from Aug 1, 2023 through Oct 8, 2023. Remember that all the values are going the be the exchange rates as compared to the Euro.  
* Make a DataFrame of the results with the date as the column index, and columns for each currency code (excluding EUR).  Data should be sorted by index.  

|          | MXN | BRL | HUF | KRW | ZAR | NZD | AED | USD |
|----------|-----|-----|-----|-----|-----|-----|-----|-----|
|2023-08-01|     |     |     |     |     |     |     |     |
|2023-08-02|     |     |     |     |     |     |     |     |
|  ...     |     |     |     |     |     |     |     |     |
|2023-10-08|     |     |     |     |     |     |     |     |

* *Hint*:  Pandas DataFrames have an `.T` attribute which takes the transpose of the DataFrame
* *Hint*: If `pd.json_normalize()` doesn't work well, try `pd.DataFrame()`

Which currencies have the highest positive and highest negative correlations with USD?  

**On the `answers.txt` file report:**
1. Currency Names from (A.)
2. The currency with the highest positive correlation with USD and
3. the corresponding correlation coefficient
4. The currency with the highest negative correlation with USD and
5. the corresponding correlation coefficient

**DataFrame**

{:start="6"} 
6. Save your DataFrame as a csv file called `currency_exchange.csv` (Do NOT use `index=None` because we want to keep the index in this case).  Include this file in your GitHub repository. 

**`.gitignore`**

{:start="7"} 
7. Be sure to add your api-key file to the `.gitignore` and that your actual key doesn't appear in your code.  Also add any other appropriate files and folders to your `.gitignore.`

## Part 2: Web Scraping
Using `requests`, `BeautifulSoup`, and `pandas`, create a DataFrame of the
[140 Essential Action Movies](https://editorial.rottentomatoes.com/guide/140-essential-action-movies-to-watch-now/)
as selected by Rotten Tomatoes. 

Your DataFrame should have 140 rows and 5 columns:

| Title | Year | Score | Rank | Category |
|-------|------|-------|------|----------|
|*title*|*year*|*score*|*rank*|*category*| 

where 
- "Title" is the movie title, 
- "Year" is the year the movie came out, 
- "Score" is the tomato meter score (NOT the adjusted score), 
- "Rank" is the order the movie is listed on the page from 140 down to 1 (so "Running Scared" should have rank=140; "Equilibrium should have rank=139; and so on.)
- "Category" is the rating category used by Rotten Tomatoes and should be "Certified Fresh", "Fresh", or "Rotten" 

"Title" and "Category" should be type "object". "Year","Score", and "Rank" should be type "int".

**On the `answers.txt` file report:**

{:start="8"}
8. The mean "year" 
9. The mean "score" 
10. The correlation coefficient between "score" and "rank"
11. The mean rank for each category 
* (a) Mean rank of "Certified Fresh"
* (b) Mean rank of "Fresh
* (c) Mean rank of "Rotten" 

**DataFrame**

{:start="12"} 
12. Save your DataFrame as a csv file called `action_movies.csv` (Use `index=None` because we do not want to keep the index in this case).  Include this file in your GitHub repository. 

## Part 3: Practice with APIs

**You can work in groups of 2-3 for this part - but you should work together *in-person*, not just over Discord, although Discord can be used to help set up your group.  It is not required for you to work in a group.**  
* All students in the group should still submit the dataset and question answers in their own GitHub repo.

Explore an API that we didn't cover in class.  Use ChatGPT (or similar) or just a Google search to brainstorm some popular and/or easy to work with APIs.  We can also brainstorm together in class if necessary.  

Put together a *small*  (less than 1MB) simple dataset of your choice using your selected API with at least two columns (variables or features) and at least 50 rows (observations or instances).    Include your dataset as a CSV file called `my_api_data.csv`.

Answer the following questions:

{:start="13"} 
13. What API did you explore
14. Provide a link to the API Documentation 
15. On a scale from 1(least helpful/easy to use) -- 5(most helpful/easy to use), give a rating for how helpful/easy-to-use you found the API Documentation.  Explain your answer
16. Give a brief description or bullet list that could help someone else get started with this API
17. Give a brief description of the dataset you created
18. Report the names of students you work with that will have similar answers and dataset (or "None")

**DataFrame**

{:start="19"}
19. Remember to include `my_api_data.csv` in your repo


# Submission 
Your GitHub repo should contain the following files before your final submission:
* `answers.txt`
* `currency_exchange.csv`
* `action_movies.csv`
* `my_api_data.csv`
* `.gitignore`
* Either a `.py` or `.ipynb` file that contains the work for your lab.  Please keep your code neat and well documented. 

Your GitHub repo should NOT contain:
* `.DS_store` files
* `.ipynb_checkpoints`
* `__pychache__`
* `*.py[cod]`
* `*.py.class`
    
 
---
