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
Movie Data : The primary dataset used for this analysis is the "Movie Data Homework.xmls" file, containing detailed information about each movie's performance, actors, directors and more
[Movies Data Homework.xlsx](https://github.com/spevaky/MovieData/blob/bbf510e2977bf3e4fccc4afcff653b4a66a64674/Movies%20Data%20Homework.xlsx)

### Tools
 - Power Query - I used Power Query for data cleaning and organising
 - Excel, Pivot Tables - I used them for Data Analysis, Creating reports and Visualizations

### Data Cleaning ad Preparation
In the initial data preparation phase, we performed the following tasks:
 - Data loading and inspection.
 - Handling errors, missing values.
 - Data cleaning and formatting.
The excel file after the data cleaning & preparation process can be downloaded here - [Movies Data Ready for Dashboard.xlsx](https://github.com/spevaky/MovieData/blob/09bf7cecf917d4724468f18d982721acbd8fde72/Movies%20Data%20Ready%20for%20Dashboard.xlsx)
### Exploratoty Data Analysis
 - Which genres were the most profitable these years?
 - Which actors were the most successful?


### Results and Findings 
As an example:
Best profitable movie was: with Budget of... Box Office Revenue was 102,000,000 USD. The genre of this movie was...
![Best Prof Movie](https://github.com/spevaky/MovieData/blob/cbc23dfdbd86e6ea52b267a8199bb00f375d5025/Best%20Prof%20Movie.JPG)

The best actor was...
The best director...
![Movies Data Dashboard](https://github.com/spevaky/MovieData/blob/0759b09e1ffbd7f9c54dbbe9274fffe50a44f21f/Movies%20Data%20Dashboard.jpeg)

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
