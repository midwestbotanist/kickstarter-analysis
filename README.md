# kickstarter-analysis
Analyzing kickstarter data for trends
## Overview of Project

### Purpose
The Kickstarter dataset lists fundraising campaign goals and resulting pledge amounts for many different categories/subcategories. The purpose of this analysis is to compare outcomes based on launch date for theater-related campaigns, and also outcomes based on goals for specifically play campaigns.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
To analyze theater campaign outcomes based on launch dates, the Kickstarter dataset was used to generate a pivot table. The pivot table was constructed by placing the parent categories an years into Filters, outcomes into Legend, date created conversion into Axis, and count of outcomes into Values. Inside the table, the column labels were filtered to include only the successful, failed, and canceled outcomes.

The pivot table was then used to generate a line graph to show how different outcomes varied based upon the month of the year they launched. This was chart is Theater_Outcomes_vs_Launch.png

### Analysis of Outcomes Based on Goals
To analyze outcomes of campaigns for plays, a new table was created comparing the number of campaigns for successful, failed, and canceled ones, along with the percentage the outcome categories were, for 12 different levels of financial goals. This was done by using the COUNTIFS function to filter the goal amount, outcome type, and subcategory of plays from the Kickstarter dataset. Cell(2,2) used the following code:

=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")

This code was modified for the in-between amounts, as can be seen from cell (3,2):

=COUNTIFS(Kickstarter!$D:$D, ">=1000",Kickstarter!$F:$F,"successful",Kickstarter!$D:$D, "<=4999",Kickstarter!$R:$R,"plays")

Using the results from the number successful, failed, and canceled columns, the total projects at each goal amount were summed and the percentage of the total projects for each outcome was found. These percentages were then visually represented in the Outcomes_vs_Goals.png

### Challenges and Difficulties Encountered
The only struggle I had was understanding how to generate the COUNTIFS code correctly. I was attempting to draw from the pledge column in the Kickstarter dataset rather than from the goal column. 

An additional issue I had with the code was understanding the need to place the range on either side of the outcomes column rather than how I was putting both the top and bottom of the goal amount range in front of the outcome column. Upon realizing my mistake I was able to then generate the chart without issue. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
Two conclusions that can be made from the laubch date outcomes is that May is the best month to launch a campaign and trails down from there. December is the sworst month to launch a campaign.

- What can you conclude about the Outcomes based on Goals?
For outcomes based on goals, it can be concluded that lower amounts (below 10000) have a better success rate. The fail rate becomes higher than the success rate once the goal amount goes above 15000. 
 
- What are some limitations of this dataset?
A limitation to the Outcomes based on Launch Date dataset is that without including the deadline the length of time the campaign ran is not accounted for. 

A limitation for the outcomes based on goals is that over 50% of the campaigns were under 5000, so the higher goal amount have results generated from a much smaller sample size and thus might not be as accurate of a predictor. 

- What are some other possible tables and/or graphs that we could create?
Another graph to create could be outcomes based on length of campaign, using the same format as the Outcomes Based on Goal table/graph. 
