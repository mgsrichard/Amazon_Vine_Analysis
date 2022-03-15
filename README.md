# Amazon_Vine_Analysis
Using Spark and AWS RDS to analyze Amazon Vine reviews

## Overview

This  week, we used PySpark to analyze larger data files. Using AWS, PySpark, and PostgreSQL/pgAdmin, I downloaded a dataset of Amazon reviews of electronics from an S3 bucket, and used PySpark to clean the data and create data frames to export into tables in PostgreSQL. Then I loaded 4 tables into a PostgresSQL database. The dataset contained reviews of electronics purchased on Amazon. A portion of the reviews were through a Vine program which paid for a review, and the others were normal, unpaid reviews not part of the Vine program. I exported the Vine reviews table into Jupyter Notebook and used Python/Pandas to analyze it. The purpose of this analysis is to determine if the paid reviews have a bias toward positivity; in other words, did paying for the review make it more likely to be a positive review.

## Results
We filtered the reviews to use only reviews that had more than 20 votes, and where 50% or more of the votes were helpful votes. Then we anayzed this group of reviews based on whether it was a paid Vine review or a non-paid review, and counted the number of 5 star reviews in each group. The results of our analysis are as follows:
  - In our filtered data there were 1,080 Vine reviews and 49,659 non-Vine reviews.
  - Of the Vine reviews, 454 were 5 star reviews. Of the non-Vine reviews, 23,034 were 5 star reviews.
  - 42% of the paid Vine reviews were 5 star reviews, and 46% of the non-paid, non_vine reviews were 5 star reviews

## Summary
These results indicate that there is no positivity bias for reviews in the Vine program. The non-Vine reviews had a higher percentage of 5 star reviews, 46%, versus the 42% of 5 star reviews in the Vine reviews. If we wanted to expand our analysis, we could examine the number of 4 and 5 star reviews to see how the ratings compare of 4 star reviews only and 4 and 5 star reviews combined. Additionally, we could import our data into R and perform a 2 sample t-test to determine if the mean ratings among the two groups are statistically similar.

## Supporting Images

Below are images of the data imported into the four tables in our database. Only the Vine table was used in this analysis.

### Customer table
![customers](https://github.com/mgsrichard/Amazon_Vine_Analysis/blob/main/images/customers_table.png) <br>

### Products table
![products](https://github.com/mgsrichard/Amazon_Vine_Analysis/blob/main/images/products_table.png)<br>

### Review ID table
![review id](https://github.com/mgsrichard/Amazon_Vine_Analysis/blob/main/images/review_id_table.png)<br>

## Vine table
![vine](https://github.com/mgsrichard/Amazon_Vine_Analysis/blob/main/images/vine_table.png)
