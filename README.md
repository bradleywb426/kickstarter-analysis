# An Analysis of Kickstarter Campaigns
Analyzing data from US-based campagins of Kickstarters for plays to uncover trends in successful and failed campaigns

## Overview
Louise just finished her Kickstarter Campaign for her play, *Fever*. Now, she wants comparisons on other Kickstarter campaigns for plays and their outcomes. To accomplish this, we have looked through a dataset of Kickstarter Campaigns and filtered to look at other plays, and then analyzed their outcomes based on their Campaign launch date and their funding goal. 

## Analysis and Challenges

### Analysis of Outcomes based on Launch Date

To begin the analysis on Kickstarter Campaign Outcomes based on Launch Date, the dataset was first imported into a Pivot Table. Each row in the Pivot Table represents one month in a calender year, and each column represents either all Campaigns of a given outcome (i.e., successful, canceled, failed) in a specific month or the Grand Total of all campaigns that launched in said month. The Pivot Table is then filtered to only show the data from Campaigns in the "Theater" parent category, which is then used to create a Pivot Chart. The Pivot Chart is a line chart that shows how many Campaigns of each outcome occured in a given month over all years of data, and has a marker on each line at every month.

<img src="https://github.com/bradleywb426/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png" width="600">

### Analysis of Outcomes based on Goals

The analysis of Campaign Outcomes based on Goals started by creating an empty table where each row represents a different bracket of goal amounts. The goal brackets were "less than $1000", "from $1000 to $49999", and "greater than $50000", and the data from $1000 to $49999 was broken further into brackets of $5000 width (i.e., $1000 to $4999). The columns of the table represent the number of each Campaign outcome for each goal bracket. These columns were populated using "COUNTIFS" functions like the following:

```
=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$F:$F,"Successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,"<=4999")
```
This particular function first checks our Kickstarter data for Campaigns that have a value of greater than or equal $1000 in the "Goal" column, and then checks all Campaigns that fit that criteria for "Successful" in their "Outcome" column. From there, the function finds all Campaigns that fit the previous critera and have "Plays" in the "Sub Category" column, and then excludes any Campaigns that have a goal greater than $4999. Once the "COUNTIFS" functions populate all columns with the number of each outcome for all Campaigns in a given goal bracket, a new column is created of the Total Number of all Campaigns in a given goal bracket. This is done by adding together the previous columns using the "SUM" function. The percentage of each outcome was calculated by dividing the number of campaigns of a certain outcome in a given bracket by the Total Number of campaigns in a said bracket. These precentages were than used with the brackets to plot a line graph of the data.

<img src="https://github.com/bradleywb426/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png" width="1000">

### Challenges and Difficulties Encountered

No challenges were encountered during these analyses, though many potential difficulties were considered and avoided. A primary potential difficulty was over or under filtering, as either path could substantially alter the analysis of the dataset and lead to poor recommendations. Another hazard was avoiding using an incorrect function for a task or mistyping a function, which could hinder the analysis of the data or lead to an incorrect analysis of the data. Another problem could arise through using inappropriate data for an analysis or using the correct data incorrectly, which can lead to an irrelevant or incorrect analysis.

## Results

Looking at the Launch Date Outcomes, we can see that the level of cancellations is relatively low and constant year round. The number of failed and successful campaigns follow a similar pattern for most of the year, though there are more successes each month than failures. The greatest gap between successful and failed campaigns is from Late Spring through Summer, where the two months with the largest gap being in May and June. Looking at the Outcomes based on Goals, there is a general negative trend where the percentage of succesful campaigns decreases as goal increases. Conversely, there is a positive trend of higher percentage of failed campaigns as goal amounts increase. While the percentages of successes outweigh failures in the $10000 - $14999 bracket, which is where Louise's campaign lies, the difference is rather small. The highest percent of successes happen with goals less than $4999.

Some limitations of this data become apparent in the analysis based on goals, as the data appears to say that campaigns between $35000 and $44999 seem to be very successful. However, this is due to the relatively few number of campaigns over $10000. With more data, clearer and more accurate predictions could be made based on goal amounts. Another prominent limitation of the dataset is the lack of data within the past 5 years. This means any relatively recent trends that could influence predictions over how future campaigns could go, especially the near future, will not be accounted for. 

To help make up for these limitations, other aspects of the data could be further analyzed. The statistics of the "play" sub category could be calculated and explored to find out if Louise's campaign is an outlier amongst similar campaigns when looking at goal amounts, and potentially how much of an outlier it might be. This could then be further explored by comparing Louise's pledges to the total amount pledged to similar campaigns to again see how Louise's campaigns fits in. It could also be worthwhile to further explore the different genres of Play Kickstarter campaigns, and see if certain genres are more or less likely to be backed as well as how much each genre receives in pledges.
