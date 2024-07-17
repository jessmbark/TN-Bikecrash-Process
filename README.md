# TN-Bikecrash-Process
 The data, notebooks, and process notes for TN-Bikecrash-Project
 ---
 ### As of right now, this is subject to change before deadline. As I write this, I am realizing that I think I can pull more from the data. 
 ## Content Description
I called this project "Hell on Two Wheels: An 15-year analysis of bicycle crashes in Tennessee." I had initially planned on creating a project centering a map of the state's bicycle routes, with each route graded on an A-F scale, but I could not get the map to work, so I pivoted when I found the dataset included in the Updated TN bike crashes PDF found in this repo. I saw a comment from Soma in the #helpme Slack channel with a link to [this](https://github.com/jsoma/github-actions-pdf-tables/blob/main/PDF%20table%20extraction.ipynb) repo and decided to use pdfplumber to explore the table in this pdf.

I found that injury crashes make up the majority of all bicycle crashes in Tennessee since 2010 and that the state has not really improved its crash numbers over the course of the past 14 years. I also found that of Tennessee's 95 counties, Shelby County has both the most total bicycle crashes and the most fatal crashes out of all counties in the state. (For reference, Memphis is the seat of Shelby County).

## Finding and analyzing the data

First, I found the PDF containing the table I wanted by Googling "bike crashes in Tennessee." I had initially found [this dataset,](https://www.tn.gov/content/dam/tn/safety/documents/Bicyclists.pdf) but it only had data through 2020, so I kept looking until I found the more updated version. As great as that was, once I plotted out the time data, I realized that I could not use 2024 to tell a time story because 2024 is not finished yet while all other years are. 2023 was an incredibly crash-heavy year for cyclists and Tennessee has not had major infrastructure updates, so I cannot imagine the downward trend is true. So I cut it.

Almost straight away, I needed some help working with pdfplumber. I found that I could get the table from the first page with ease or the last page, but not all pages. I could not be more thankful for the TAs that helped me along the way as they talked me through writing that initial code. Once they helped me get a good scrape, I was in business.

From there, this table required quite a bit of cleaning. Cleaning turned up a lot of warnings, which was mildly concerning, but things still worked, so I did not let it slow me down. I think pdfplumber automatically pulls all columns are strings, so I had to change everything so that I could actually do math. I also renamed columns to prevent myself from getting confused. I used pandas to find the county with the most crashes and the most fatal crashes. Because those were the same county, I decided to save both the dataframe of year totals and that county as CSV files so that I could visualize them with Flourish.

I chose Flourish because it was a tool I had not used before, and I think it's okay. It felt like Datawrapper in a different font.

## Wins & Losses
I used new tools! I think I love pdfplumber. Not sure if [jsvine](https://github.com/jsvine) will talk about it in class, but if he doesn't, I will spread the good word myself. (Ironically, Soma's page said suggested that Camelot might be easier to work with, but I truly could not get Camelot to work. PDFPlumber 4 lyf.) Even though I think Flourish is just okay, I am still glad that I used it! I think it, and more confidence, helped make slightly more interesting visualizations than the [first project](https://jessmbark.github.io/TN-Library-Project/). I hope to use at least one new tool outside of a homework context per project.

This README cannot possibly contain how sad I am that my map did not work out in time. I sincerely hope that it does for the final project. I also think that I somehow struggled with timing more for this project than the first, which meant that I felt like I got a lot less out of the data even if my visualizations were at least kind of cool.
