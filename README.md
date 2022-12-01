# An Analysis of Kickstarter Campaigns
Analyzing data from Theater and Play Kickstarter campaigns to uncover trends in successful and failed campaigns

## Overview
Louise just finished her Kickstarter campaign for her play, *Fever*, and now wants to compare her campaign with the outcomes of similar campaigns. To accomplish this, we have looked through a dataset of Kickstarter campaigns and filtered it to look at other theater and play campaigns, and then analyzed their outcomes based on their campaign launch date and funding goal.

## Analysis and Challenges

### Analysis of Outcomes based on Launch Date

To begin the analysis of Kickstarter campaign outcomes based on Launch Date, the dataset was first imported into a Pivot Table where each row in the Pivot Table represents one month in a calendar year.  The columns represent each campaign outcome for all campaigns launched in a given month as well as an additional column for the Grand Total of all campaigns launched for a given month. The Pivot Table is then filtered to only show the data from Campaigns in the "Theater" parent category, and the filtered data is used to create a Pivot Chart. This Pivot Chart is a line chart comparing the number of each campaign outcome in a given month over all years of data and has markers on each line to denote each month.

<p align="center">
<img src="https://github.com/bradleywb426/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png" alt="Theater Outcomes based on Launch Date" width="600">
</p>

### Analysis of Outcomes based on Goals

The analysis of campaign outcomes based on Goals started by creating an empty table where each row represents a different bracket of goal amounts. The goal brackets were "less than $1000", "from $1000 to $49999", and "greater than $50000", where the data from $1000 to $49999 was broken further into brackets of $5000 width (e.g., $1000 to $4999). The columns of the table represent the number of each Campaign outcome for each goal bracket. These columns were populated using "COUNTIFS" functions like the following:

```
=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$F:$F,"Successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,"<=4999")
```
This particular function first checks the data for campaigns that have a value of at least $1000 in the "Goal" column and then checks those campaigns for any that have "Successful" in their "Outcome" column. From there, the function further checks those campaigns for “Plays” in the “Sub Category” column, and then further excludes any of those campaigns that have a goal greater than $4999. After the “COUNTIFS” functions populate the number of outcome columns, a new column was created for the Total Number of all campaigns in a given goal bracket. This column was populated by adding the number of each outcome in a given bracket together using the “SUM” function. From there, additional columns for the percentage of each outcome in a given bracket were created. The percentage columns were calculated by dividing the number of specific outcomes in a given bracket by the total number of campaigns in a said bracket. A line chart was then created using the percentages in each bracket.

<p align="center">
<img src="https://github.com/bradleywb426/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png" alt="Theater Outcomes Based on Goal Amount" width="1000">
</p>
  
### Challenges and Difficulties Encountered

No challenges were encountered during these analyses, though many potential difficulties were avoided. The primary potential difficulty was over or under-filtering, as either path could substantially alter the analysis of the dataset and lead to poor future recommendations. Another hazard was avoiding using an incorrect function for a task or mistyping a function, which could hinder the analysis of the data or lead to an incorrect analysis of the data. Another problem could arise through using inappropriate data for analysis or using the correct data incorrectly, which can lead to an irrelevant or incorrect analysis.

## Results

### Results based on Analyses

Looking at the Launch Date outcomes, we can see that the level of cancellations is relatively low and constant year-round. The number of failed and successful campaigns follows a similar pattern for most of the year, though there are more successes each month than failures. The greatest gap between successful and failed campaigns is from Late Spring through Summer, where the two months with the largest gap are May and June. Looking at the outcomes based on goals, there is a general negative trend where the percentage of successful campaigns decreases as the goal increases. Conversely, there is a positive trend of a higher percentage of failed campaigns as goal amounts increase. While the percentages of successes outweigh failures in the $10000 - $14999 bracket, which is where Louise's campaign lies, the difference is rather small. The highest percent of successes happen with goals of less than $4999.

### Limitations of Dataset

Some limitations of this data become apparent in the analysis based on goals, as the data appears to say that campaigns between $35000 and $44999 seem to be very successful. However, this is due to the relatively few campaigns over $10000. Clearer and more accurate predictions could be made based on goal amounts with more data. Another prominent limitation of the dataset is the lack of data within the past 5 years. This means any relatively recent trends that could influence predictions over how future campaigns could go, especially in the near future, will not be accounted for.

### Further Analysis

To help make up for these limitations, other aspects of the data could be further analyzed. The statistics of the "play" sub-category could be calculated and explored to find out if Louise's campaign is an outlier amongst similar campaigns in terms of goal amounts, and potentially how much of an outlier it might be. This could then be further explored by comparing Louise's pledges to the total amount pledged to similar campaigns to again see how Louise's campaigns fit in. It could also be worthwhile to further explore the different genres of play Kickstarter campaigns, and see if certain genres are more or less likely to be backed as well as how much each genre receives in pledges.
