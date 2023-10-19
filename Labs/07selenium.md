---
title: "Lab 7: Scraping JavaScript"
layout: single
author_profile: false
classes: wide
excerpt: 
---

## Lab 7: Practice with Selenium

For this homework assignment you will practice web scraping using Python and Selenium to extract data from the Audible.com website. In this assignment, you will write a Python script to scrape information books on Audible.com and then analyze and present the data in a structured format.


1.  Update Selenium if you haven't already done so:
```bash
# in terminal with class environment activated
conda install -c conda-forge selenium=4.14
```
2. Install webdriver-manager if you haven't already done so:
```bash
# in terminal with class environment activated
pip install webdriver-manager
```
3.  Using Selenium, create a DataFrame of the [bestselling](https://www.audible.com/adblbestsellers?ref_pageloadid=h7Ag5cGcQ5yvRAVu&ref=a_search_b1_desktop_footer_column_2_0&pf_rd_p=6a55a63d-48d3-4d5e-857f-ae6682380e4d&pf_rd_r=65QXM553SAAQNRH2VDV2&pageLoadId=yGFSdjIrgVpQDcAP&ref_plink=not_applicable&creativeId=2d835e86-1f10-4f6e-a4c6-33d2001684e6) audio books on audible.

Your DataFrame should have 100 rows and 5 columns:

| title | author | runtime | release_date | list_number |
|-------|------|-------|------|----------|
|*title*|*author*|*runtime*|*release_date*|*list_number*| 

where 
- "title" is the book title, 
- "author" is author of the book 
- "runtime" is the length of the audio book
- "release_date" is the release date of the audio book
- "list_number" is the number that the audio book appears on the list

4.  Save you DataFrame as a `.csv` file called `audiobooks.csv` and commit it in your repository
