# An Analysis of Kickstarter Campaigns
Analyzing data from US-based campagins of Kickstarters for plays to uncover trends in successful and failed campaigns

## Overview
Louise just finished her Kickstarter campaign for her play, *Fever*. Now, she wants comparisons on other Kickstarter campaigns for plays and their outcomes. To accomplish this, we have looked through a dataset of Kickstarter campaigns and filtered to look at other plays, and then analyzed their outcomes based on their campaign launch date and their funding goal. 

## Analysis and Challenges

### Analysis of Outcomes based on Launch Date

To begin the analysis on Kickstarter Campaign Outcomes based on Launch Date, the dataset was first imported into a Pivot Table. Each row in the Pivot Table represents one month in a year, and each column represents an outcome of a campaign (i.e., successful, canceled, failed) and the Grand Total of all campaigns that launched in a given month. The data in the Pivot Table is then filtered to only show the data from campaigns in the "Theater" parent category. The filtered data was then used to create a Pivot Chart in the Line Chart with Marker format.

<img src="https://github.com/bradleywb426/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png" width="600">

### Analysis of Outcomes based on Goals

The analysis of Campaign Outcomes based on Goals, an empty table was created where each row is a different bracket of goal amounts. The brackets were less than $1000, from $1000 to $49999, and greater than $50000, and the data from $1000 to $49999 was broken further into brackets of $5000 width. The columns of the table represent the number of each campaign outcome for each bracket. These columns were populated using "COUNTIFS" functions like the following:

```
=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$F:$F,"Successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,"<=4999")
```
Explain the Code a little. A new column was then created that displayed the Total Number of campaigns for each Bracket using the "SUM" function. Then, using the found number of each campaign outcome per bracker and the calculated total, the percentage of each outcome for each bracket was calculated. These precentages were than used with the brackets to plot a line graph of the data.

<img src="https://github.com/bradleywb426/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png" width="1000">

### Challenges and Difficulties Encountered

No challenges were encountered during these analyses, though many potential difficulties were considered and avoided. A primary potential difficulty was over or under filtering, as either path could substantially alter the analysis of the dataset and lead to poor recommendations. Another hazard was avoiding using an incorrect function for a task or mistyping a function, which could hinder the analysis of the data or lead to an incorrect analysis of the data. Another problem could arise through using inappropriate data for an analysis or using the correct data incorrectly, which can lead to an irrelevant or incorrect analysis.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
- Looking at the outcomes of the campaigns based on Launch Date, we can see that the failure rate follows the same general pattern as the success rate. The time of the largest difference in failure rates and success rates is from the Late Spring to Summer. This corresponds with May to August, and the most successful months are May and June.

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?
  - Limited Data in Mid to High range
  - No recent data

- What are some other possible tables and/or graphs that we could create?
  - Parent/sub category
  - Descript Stats Plots

---

---


## Breakdown of Campaign Outcomes based on Category

Looking at the breakdown of Kickstarter campaign outcomes in the US, we can see that "Theater" is the most numerous category with over 900 entries (912 to be exact). Subsequently, "Theater" also has the most successes and failures with over 500 successful campaigns and over 300 failed campaigns (specifically 525 and 349 respectfully). 

Furthering our view into the Subcategories of "Theater" we can see that "Plays" are the most numerous, with almost 700 different campaigns. "Plays" also had the highest success rate of the subcategories with around 400 successes (412 successes) and about 60% success rate (61.4% to be exact).

## Statistics of Goals and Pledges

These Box and Whisker Plots showcase the statistics of the Successful and Failed Play Kickstarters in the US. The goal of $10000 is above the highest value of the upper range of Successful Campaigns, but is almost the mean value of goals for Failed Campaigns. Looking at the same type of plot applied to the Pledges of Successful and Failed Play Kickstarters in the US tells a similar story.

The Pledges for Successful campaigns has the same shape of spread as the Goals, though the range is shifted towards higher values. 

## Recommendations
Based on the previous analyses, it is recommeneded that Fever's Kickstarter campaign is launched in the late Spring (April to May) with a Goal of less than $8500, which is the highest value pledged to campaigns similar to Fever's in the US.
