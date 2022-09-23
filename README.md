# Amazon Vine Analysis with PySpark, Amazon RDS, and Postgres

## Overview

The client, SellBy, is considering joining the Amazon Vine program, a paid service that allows companies to receive reviews for their products. This project analyzes data from the Amazon Vine program to determine if there is a favorable bias from the paid, Vine reviewers. Of the 50 available datasets, this analysis uses the US reviews for sports products. The data is extracted from the Amazon RDS instance, transformed using PySpark in a Google Colab Notebook, and loaded into pgAdmin. Metrics were calculated with PySpark.

## Resources

- **Data Source:** [Amazon US Sports Review Dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Sports_v1_00.tsv.gz)
- **Resources:** Google Colab Notebook, Postgres 13.7, pgAdmin 4, AWS

## Results

Before comparing the paid, Vine reviews with the unpaid reviews, I filtered the data to only show reviews with total votes greater than or equal to 20 to avoid dividng by zero. Additionally, I filtered the data to only show reviews that were considered at least at a 50% helpful.

#### Total number of reviews
Of the 61,948 reviews, 334 were paid, Vine reviews and 61,614 were unpaid, non-Vine reviews.
| Vine Reviews      | Non-Vine Reviews     |
|-------------------|-----------------------|
|![Screen Shot 2022-09-23 at 4 55 21 PM](https://user-images.githubusercontent.com/106405775/192061975-c844269d-6292-4266-bf6d-629982b0a91c.png)| ![Screen Shot 2022-09-23 at 4 55 31 PM](https://user-images.githubusercontent.com/106405775/192062010-d755fd36-a59a-47bd-8fbc-7c614da952ff.png) |

#### Number of 5 Star Reviews 
Of the 32,804 reviews, 139 were paid, Vine reviews and 32,665 were unpaid, non-Vine reviews.
| Vine Reviews      | Non-Vine Reviews     |
|-------------------|-----------------------|
|![Screen Shot 2022-09-23 at 4 58 53 PM](https://user-images.githubusercontent.com/106405775/192062344-8aa8e889-bf31-47c6-9c08-d202d6cdd324.png)| ![Screen Shot 2022-09-23 at 4 59 06 PM](https://user-images.githubusercontent.com/106405775/192062377-5e1fe8aa-b60d-4ea6-98d8-1fe3e4f707ce.png)|

#### Percentage of 5 Star Reviews
Out of the 334 paid, Vine reviews, 41.6 were 5 star reviews. Out of the 61,614 unpaid, non-Vine reviews, 53.0% were 5 star reviews.
| Vine Reviews      | Non-Vine Reviews     |
|-------------------|-----------------------|
|![Screen Shot 2022-09-23 at 5 03 40 PM](https://user-images.githubusercontent.com/106405775/192062765-7b7d7ea5-9071-4896-a560-1372a6128604.png)| ![Screen Shot 2022-09-23 at 5 03 46 PM](https://user-images.githubusercontent.com/106405775/192062805-04c83172-acf0-4497-812c-a49911a2dd3a.png)|

## Summary

Only 41.6% of Vine reviews for sports products were 5 star reviews. Compared to the 53.0% of non-Vine reviews, there is not a positive bias toward the Amazon Vine program. 

#### Different Datasets
Running this code with other datasets, like video games, books, or personal care products, would help to determine if sports is an outlier and there is a positive bias for other types of products. SellBy may also consider running this code on a dataset that most closely fits with their products.

#### Statistical Distributions of Star Ratings
In addition to comparing other datasets, SellBy may want to analyze the statistical distribution of the star rating for the paid, Vine and unpaid, non-Vine reviews. The distribution would determine if the distribution was normal or skewed. 
