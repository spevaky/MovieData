# Movie Data Analysis Project
## Table of Content:
 - [Project Overview](#project-overview)
 - [Data Source](#data-sources)
 - [Results](#results-and-findings)
 - [Challenges in Analysis](#challenges-in-analysis)

### Project Overview
This data analysis project aims to provide insights into the performance and trends of movies from 2012 to 2016.
By analyzing various aspects of the movie data, we seek to identify patterns, make data-driven recommendations, and gain a deeper understanding of the industry's dynamics.

### Data Sources
Movie Data : The primary dataset used for this analysis is the "Movie Data Homework.xmls" file, containing detailed information about each movie's performance, actors, directors etc.
[Movies Data Homework.xlsx](https://github.com/user-attachments/files/16385247/Movies.Data.Homework.xlsx)

### Tools
 - Power Query - I used Power Query for Data Cleaning
 - Excel, Pivot Tables - I used them for Data Analysis, Creating reports and Visualizations

### Data Cleaning ad Preparation
In the initial data preparation phase, we performed the following tasks:
 - Data loading and inspection.
 - Handling errors, missing values.
 - Data cleaning and formatting.
The excel file after the data cleaning & preparation process can be downloaded here - [Movies Data Ready for Dashboard.xlsx](https://github.com/user-attachments/files/16385260/Movies.Data.Ready.for.Dashboard.xlsx)
### Exploratoty Data Analysis
 - Which genres were the most profitable these years?
 - Which actors were the most successful?...


### Results and Findings 
As an example:
Best profitable movie was: with Budget of... Box Office Revenue was 102,000,000 USD. The genre of this movie was...
![Best Prof Movie](https://github.com/user-attachments/assets/faa36d20-0c8e-49a7-870c-fde9076a7b4c)

The best actor was...
The best director...
![Movies Data Dashboard](https://github.com/user-attachments/assets/ff5e2ce1-a93e-4fe6-b016-15077d9af9f9)

### Challenges in Analysis
#### M Language
One of interesting features/ challenges I was working with was a specific code for Grouping in M language which enabled me to Combine genres together for further analysis.
We had 2 column for genres, but we needed to combine them and have the same format, for example action/comedy, not comedy/action.

``` 
= Table.Group(#"Sorted Rows1", {"Movie Title"}, 
                                            {{"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},
                                            {"AllData", each _, 
                                                        type table [Movie Title=nullable text, Release Date=nullable date, Wikipedia URL=nullable text, Concat Genre=nullable text, Director=nullable text, Actor First=nullable text, Actor Second=nullable text, Actor Third=nullable text, Actor Fourth=nullable text, Actor Fifth=nullable text, #"Budget ($)"=nullable number, #"Box Office Revenue ($)"=nullable number]}
                                            }
```
### Excel Dashboard
Can be downloaded here [Movies Data Dashboard.xlsx](https://github.com/user-attachments/files/16385266/Movies.Data.Dashboard.xlsx)
