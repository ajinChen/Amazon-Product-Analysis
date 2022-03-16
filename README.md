# Amazon Product Analysis
## Intro
<img src="pictures/amazondigital.png" width="350" align="right">

This is a project to analyze Amazon's digital product from different perspectives. Our team members are *Zhipeng Hong*(zhong5@usfca.edu), *Wei He*(whe13@usfca.edu), *Kaihang Zhao*(kzhao24@usfca.edu), *Jih-Chin Chen*(). This project was done during the University of San Francisco MSDS 2021 fall module.

<img src="pictures/EMR.png" width="350" align="right"> In this project, we built pipeline to access data from **AWS S3** and processed data in **AWS EMR**. Then we used **Spark RDD** to analyze **Amazon Digital Products Review** from different dimension. We used 5 instances m5.xlarge in EMR to process our raw data which supported us proccess data more faster.



## Datasets
Our original data have 
* **2.86GB+** in total
* **11,095,239** observations
* **15** relevant columns
* **5** digitalproduct categories.

| Factor | DataType | Detail |
|--------|--------|--------|
| `marketplace` | String | 2 letter country code of the marketplace where the review was written.|
| `customer_id` | Numeric | A identifier that can be used to aggregate reviews written by a single author. |
| `review_id` | Numeric | The unique ID of the review. |
| `product_id` | Numeric | The unique Product ID the review pertains to. In the multilingual dataset the reviews for the same product in different countries can be grouped by the same productid. |
| `product_parent` | Numeric | A identifier that can be used to aggregate reviews for the same product. |
|`product_title` |Text|Title of the product|
|`product_category`|Text|Broad product category that can be used to group reviews|
|`star_rating`|Numeric|The 1-5 star rating of the review.|
|`helpful_votes`|Numeric|Number of helpful votes.|
|`total_votes`|Numeric|Number of total votes the review received.|
|`vine`|Boolean|Review was written as part of the Vine program.|
|`verified_purchase`|Boolean|The review is on a verified purchase.|
|`review_headline`|Text|The title of the review.|
|`review_body`|Text|The review text.|
|`review_date`|Text|The date the review was written.|

## Data Analytics Goal
* Review with other features across category level.
* Review with other features across time level.
* Review with other features across time and category level.
* Review Content and Sentimental Score.

# Produce Analysis
We analyzed our dataset through 4 different perspectives. In order to analyze the review context, we also implemented sentimental analysis. Then we used `Plotly` a visualization tool to plot our graphs.

## Review Count and Star Rating Analysis
...
## Ratio Analysis
In this part, we analyzed click rating and helpful rating. Helpful rate is defined as the number of helpful review divided by total number of review and click rate is how likely user will click the rating for item.
We loaded data using paired-RDD and used `.cache` to persist our data into memory so that we can speed up the proccessing time. By using `groupByKey`,`map` and `count` functions, we aggrated our data and transformed data into useful insights.

## Review Analysis
...



