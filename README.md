# TN-Bikecrash-Process
 The data, notebooks, and process notes for TN-Bikecrash-Project
 ---
 ## Content Description
I called this project "A Rocky Road: An analysis of Tennessee's bicycle crash data since 2010." I had initially planned on creating a project centering a map of the state's bicycle routes, with each route graded on an A-F scale, but I could not get the map to work, so I pivoted when I found the dataset included in the Updated TN bike crashes PDF found in this repo. I saw a comment from Soma in the #helpme Slack channel with a link to [this](https://github.com/jsoma/github-actions-pdf-tables/blob/main/PDF%20table%20extraction.ipynb) repo and decided to use pdfplumber to explore the table in this pdf.

I found that injury crashes make between 80 and 92 percent of all bicycle crashes in Tennessee since 2010 and that the state has not really improved its crash numbers over time. One hundred and seventeen people have died in bicycle crashes. That comes out to a median of eight deaths per year, with over 400 crashes per year. There have been nearly 6,000 crashes across the state since data started being recorded.

## Finding and analyzing the data

First, I found the PDF containing the table I wanted by Googling "bike crashes in Tennessee." I had initially found [this dataset,](https://www.tn.gov/content/dam/tn/safety/documents/Bicyclists.pdf) but it only had data through 2020, so I kept looking until I found the more updated version. As great as that was, once I plotted out the time data, I realized that I could not use 2024 to tell a time story because 2024 is not finished yet while all other years are. 2023 was an incredibly crash-heavy year for cyclists and Tennessee has not had major infrastructure updates, so I cannot imagine the downward trend is true. So I cut it.

Almost straight away, I needed some help working with pdfplumber. I found that I could get the table from the first page with ease or the last page, but not all pages. I could not be more thankful for the TAs that helped me along the way as they talked me through writing that initial code. Once they helped me get a good scrape, I was in business.

From there, this table required quite a bit of cleaning. Cleaning turned up a lot of warnings, which was mildly concerning, but things still worked, so I did not let it slow me down. I think pdfplumber automatically pulls all columns are strings, so I had to change everything so that I could actually do math. I also renamed columns to prevent myself from getting confused. I then saved the year total data as a separate dataframe and exported that as a csv so that I could plot it in Flourish.

I chose Flourish because it was a tool I had not used before, and I think it's okay. It felt like Datawrapper in a different font. Flourish is also Corporate-ApprovedTM by my newsroom, so it felt useful to learn.

## Wins & Losses
I used new tools! I think I love pdfplumber. Not sure if Singer-Vine will talk about it in class, but if he doesn't, I will spread the good word myself. Even though I think Flourish is just okay, I am still glad that I used it! I think it, and more confidence, helped make slightly more interesting visualizations than the [first project](https://jessmbark.github.io/TN-Library-Project/). I was also stoked to get my [D3 visualization](https://jessmbark.github.io/TNbikeD3/) that I made for Youyou's class to work on this webpage. I hope to use at least one new tool outside of a homework context per project.

This README cannot possibly contain how sad I am that my map did not work out in time. I sincerely hope that it does for the final project. I also think that I somehow struggled with timing more for this project than the first, which meant that I felt like I got a lot less out of the data even if my visualizations were at least kind of cool. I think time constraints from trying to get both the map and this to work, combined with working during the program, prevented me from pulling more from the data.

An earlier version of this repo and project was going to zoom in on the county with the most crashes, but I opted to spend more time working with D3. Plus, my mentor (rightly) pointed out that county-by-county analysis would have required a per-capita analysis, and candidly, I just did not feel like doing that to tell this story. Part of me also wondered if it should be per-cyclist, not per-capita, because I don't know that Tennessee has a huge cycling population. I also don't think Tennessee keeps a cyclist registry.

That kind of analysis might work better with motorcycle data because it could be compared against the number of motorcycle licenese that a county has issued, so that might be better for a future project.
