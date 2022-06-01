# An Analysis of Kickstarter Campaigns
Analyzing data from US-based campagins of Kickstarters for plays to uncover trends in successful and failed campaigns

## Overview
Louise just finished her Kickstarter campaign for her play, *Fever*. Now, she wants comparisons on other Kickstarter campaigns for plays and their outcomes. To accomplish this, we have looked through a dataset of Kickstarter campaigns and filtered to look at other plays, and then analyzed their outcomes based on their campaign launch date and their funding goal. 

## Analysis and Challenges
god dammit i lost everything I wrote below here, fuck

### Analysis of Outcomes based on Launch Date

To analyze the dataset based on Launch Date, all of the data was first imported into a Pivot Table. Each row of the table represented one month in the year. Each column represented the number of each different outcome of a Kickstarter that ended in a given month, as well as the total number of Kickstarters that ended in a given month. The data was then filtered to only show campaigns of the "Theater" parent category. Using the Filtered Data, a pivot line chart with markers was then created.

<img src="https://github.com/bradleywb426/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png" width="600">

### Analysis of Outcomes based on Goals

To analyze the dataset based on Goals, an empty table was created with the goals amount in different brackets. The brackets were from less than $1000, from $1000 to $49999, and greater than $50000. From $1000 to $49999 was then further broken into brackets of about $5000 width. The "COUNTIFS" function was then used to find all Kicstarters that fit our criteria in each bracket using a function like the following:

```
FUCKING COUNT CODE BULLSHIT
```

Used SUM to find total number of campaigns in a goal bracket. Calculated Percentage of each outcome in a bracket. Use Percentage and goal brackets to make a line chart.

<img src="https://github.com/bradleywb426/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png" width="1000">

### Challenges and Difficulties Encountered

No challenges were encountered, but many potential ones could have occured. Such as over or under filtering data. Misstyping functions. Choosing inappropriate data or use data incorrectly.

## Results

---

---

## Analysis and Challanges
Explain how you performed your analysis using images and links to code, as well as any challenges you encountered and how you overcame them. If you had no challenges, describe any possible challenges or difficulties that could be encountered.
### Analysis of Outcomes based on Launch Date
Looking at the outcomes of the campaigns based on Launch Date, we can see that the failure rate follows the same general pattern as the success rate. The time of the largest difference in failure rates and success rates is from the Late Spring to Summer. This corresponds with May to August, and the most successful months are May and June.

### Analysis of Outcomes based on Goals

## Challenges and Difficulties Encountered

## Results
- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?
  - Limited Data in Mid to High range
  - No recent data

- What are some other possible tables and/or graphs that we could create?
  - Parent/sub category
  - Descript Stats Plots


## Breakdown of Campaign Outcomes based on Category
![Parent Category Outcomes](https://user-images.githubusercontent.com/72563705/171232082-14736fc9-0bfb-445e-b041-df170e95471c.png)

Looking at the breakdown of Kickstarter campaign outcomes in the US, we can see that "Theater" is the most numerous category with over 900 entries (912 to be exact). Subsequently, "Theater" also has the most successes and failures with over 500 successful campaigns and over 300 failed campaigns (specifically 525 and 349 respectfully). 

![Subcategory Outcomes](https://user-images.githubusercontent.com/72563705/171234265-c14180f4-c064-4ea3-b69d-c07cee4135ac.png)
Furthering our view into the Subcategories of "Theater" we can see that "Plays" are the most numerous, with almost 700 different campaigns. "Plays" also had the highest success rate of the subcategories with around 400 successes (412 successes) and about 60% success rate (61.4% to be exact).

## Breakdown of Campaign Outcomes based on Launch Date
![Launch Date Outcomes](https://user-images.githubusercontent.com/72563705/171235532-1d4c1dd9-382d-4f6c-95a9-d50ef9bc663b.png)

Looking at the outcomes of the campaigns based on Launch Date, we can see that the failure rate follows the same general pattern as the success rate. The time of the largest difference in failure rates and success rates is from the Late Spring to Summer. This corresponds with May to August, and the most successful months are May and June.

## Statistics of Goals and Pledges
![Goal Stats](https://user-images.githubusercontent.com/72563705/171253654-f7ecf4a9-6cc7-42fe-b23c-dad53e8b1204.png)

These Box and Whisker Plots showcase the statistics of the Successful and Failed Play Kickstarters in the US. The goal of $10000 is above the highest value of the upper range of Successful Campaigns, but is almost the mean value of goals for Failed Campaigns. Looking at the same type of plot applied to the Pledges of Successful and Failed Play Kickstarters in the US tells a similar story.

![Pledge Stats](https://user-images.githubusercontent.com/72563705/171260249-fa512bd5-eb5e-45a8-b95e-543732b599fb.png)

The Pledges for Successful campaigns has the same shape of spread as the Goals, though the range is shifted towards higher values. 

## Recommendations
Based on the previous analyses, it is recommeneded that Fever's Kickstarter campaign is launched in the late Spring (April to May) with a Goal of less than $8500, which is the highest value pledged to campaigns similar to Fever's in the US.
