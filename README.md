# Amazon Vine Program Reviews Analysis

## Overview of the analysis
This analysis was conducted using data collected by Amazon and available from their S3 (Simple Storage Service) as a public dataset.  Over 50 datasets on reviews of a variety of
product categories, with data on reviews by Vine Program participants and non-Vine participants.  Vine Program participants are paid for their reviews, whereas non-Vine
participants are not paid.  The purpose of this study was to determine if being paid to write reviews has an effect on the sentiment of the reviews.  

This study only looked at one Amazon S3 dataset on musical instruments.  The Amazon s3 dataset was extracted into an AWS database and then passed through a Google Colab
PySpark(v.3.1.1) notebook, where it was loaded into a PostgreSQL (v4.4) database.  Some transformation of data was done by producing tables in PostgreSQL and then read into
another Colab PySpark notebook to process into dataframes and to produce the following results.(Images of the PostgreSQL tables are included at the end of this document.)

## Results
The following statistics were generated to compare the two groups of review writers.

### Number of Vine reviews and non-Vine reviews (see images for Percentages, below, which contain these figures)
  * Non-vine reviews: 14477 
  * Vine reviews: 60

### Number of 5-star Vine and non-Vine reviews
  * Non-vine 5-star reviews: 8212 [https://github.com/CaroShaf/Amazon_Vine_Analysis/blob/main/images/nonvine5df%26tot.png]
  * Vine 5-star reviews: 34 [https://github.com/CaroShaf/Amazon_Vine_Analysis/blob/main/images/vine5df%26tot.png]
  
### Percentage of Vine and non-Vine 5-star reviews were 5 stars
  * Non-vine percentage of 5-star reviews: 56.72 [https://github.com/CaroShaf/Amazon_Vine_Analysis/blob/main/images/nonvinetot%26percent.png]
  * Vine percentage of 5-star reviews:56.66 [https://github.com/CaroShaf/Amazon_Vine_Analysis/blob/main/images/vinetot%26percent.png]
  
## Summary
Based on the information presented above, it would appear that there is no bias towards positive reviews by Vine Program (paid) participants.  In fact, there is almost no
difference at all.  However, the number of reviews by Vine participants is quite small, so it may be misleading for that reason.  It would be worthwhile to determine if the
sample dataset of Vine reviews is large enough to reject the null hypothesis and look at correlations between Vine/non-Vine membership (A/B) and percent 5-star reviews. 
Furthermore, looking at reviews of other products would be useful to see if trends are similar across the different product categories.

#### References to PostgreSQL tables
  1 customers_table [https://github.com/CaroShaf/Amazon_Vine_Analysis/blob/main/images/customers_table.png]
  2 products_table [https://github.com/CaroShaf/Amazon_Vine_Analysis/blob/main/images/products_table.png]
  3 review_id_table [https://github.com/CaroShaf/Amazon_Vine_Analysis/blob/main/images/review_id_table.png]
  4 vine_table [https://github.com/CaroShaf/Amazon_Vine_Analysis/blob/main/images/review_id_table.png]

