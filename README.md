# Food Claims Process

Vivendo, a prominent fast-food chain in Brazil boasting a network of over 200 outlets, occasionally faces compensation claims from customers who have experienced food poisoning incidents. To efficiently handle these claims, the company's dedicated legal team operates from four distinct office locations. With an unwavering commitment to enhancing customer satisfaction, the legal department's leader seeks an insightful report that delves into the varying claim resolution times across these different locations.

An exploratory analysis on each column in the dataset was performed to understand its values. Below are the findings:

Claim ID: There are 2000 values that make up the whole dataset as each row is the unique identifier. There are no missing values due to the database structure. No changes were made to this column.

Time To Close: All of the 2000 values in this column are positive. There were no missing values. No values were replaced with the overall median time to close.

Claim Amount: The values in total are in the currency fo Brazil and rounded to two decimal places. There were no missing values so no changes were made to this column.

Amount Paid: There are 36 values that are not rounded to two decimal places, instead are whole numbers. Nonetheless, the values match the description. In addition, 36 values are also null. All missing values were replaced with the overall median amount paid.

Location: This column has four categories, that match those in the description. There were no missing values and no changes were made to this column.

Individuals On Claim: This column has all values where the minimum is one, which matches the description. There were no missing values and no changes were made to this column.

Linked Cases: All of the values for the majority in this column were either TRUE or FALSE. There were 26 values that were missing. All missing values were replaced with False.

Cause: Most of the values fit the description of the three categories. There were no missing values, however there were extra categories. that either were all uppercase or had extra whitespace. These were manipulated to match the three main categories.

<img width="400" alt="claims_vs_location" src="https://github.com/eduardo20calvo/Food_Claims_Process/assets/104874384/0ce53d71-4359-493b-83bf-b049a11abe4d">

There are four possible locations in this data. Based on the bar graph above, the location with the most number of claims is RECIFE, with SAO LUIS being second with slightly more than half as many observations. Looking further into the graph, the observations are not balanced across the variable locations, with most claims coming from RECIFE and SAO LUIS. This graph supports that the legal team should focus on the city of RECIFE to improve customer replies and closing claims much efficiently.

As the legal team thinks that the claims taking the longest to close should be of most concern, we should look at how each claims' time completion are distributed. 

Looking at the count of each time completion period, we can see below that most claims take about 160 - 200 days to complete. The distribution on the time to close is right skewed. There are some outliers that take more than 300 days (almost a year) to complete. However, from the data, this is uncommon. 

When determining on which claims to improve on, they should focus on claims that average at least about 160 - 200 days. However, the legal team may choose to look into claims that take longer for further investigation if they wish. 

<img width="400" alt="time_to_close_distribution" src="https://github.com/eduardo20calvo/Food_Claims_Process/assets/104874384/a5bbda6c-6f6c-4891-a232-a70bba31ef70">

Finally, we want to show the correlation between location and the time to close on these claims. So far, claims in RECIFE that take at least about 160 - 200 days to close would be ideal to focus but we need to further look at the two variables together to see if it still stands.

When looking at the graph below, we can see there are many outliers above the box plot for each location. In addition, the interquartile range for each location look very similar. We can filter the 'time_to_close' column to only include claims between 70 and 300 days. 

<img width="400" alt="close_vs_location" src="https://github.com/eduardo20calvo/Food_Claims_Process/assets/104874384/e0ce96d6-8ec9-432f-86f8-6db9b8e62b39">

After we remove the outliers we can focus on the main range of data. The interquartile range for all the locations still look very similar after the change. We can note that the interquartile range for SAO LUIS is smaller than the other locations. This suggests that there is less variablity in the time to close on these claims. With RECIFE having the most claims with completion time of about 160 - 200 days, the graph below doesn't seem to support the idea that legal team should just focus on claims from RECIFE. 

<img width="400" alt="close_vs_location_modified" src="https://github.com/eduardo20calvo/Food_Claims_Process/assets/104874384/9d07ce62-2c1a-4372-ad48-381e781c850f">

Based on all the above, we recommend the legal team to focus on all locations with claims that take at least 160 - 200 days to complete. But the team should have an open mind to focus solely on RECIFE as they have the most number of claims amongst other locations and within the range of 160 - 200 days. Further analysis should be done to understand if claim amount also impacts the time it takes to close claims. The legal team should also consider on other factors such as the cause of the claim, in order find its correlation on the region. They can determine if there is a major food problem in each region.
