# Amazon Vine Analysis
In this project, we analyze Amazon reviews written by members of the paid Amazon Vine program to determine if there is any bias toward favorable reviews from Vine members in a selected dataset. The data set contains reviews of a specific product, from clothing apparel to wireless products. First, PySpark was used  to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Then PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset.

### The data
The [Data set](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Gift_Card_v1_00.tsv.gz) was obtained from the [Amazon review datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt). The selected data set has 15 columns ans the following images shows the information about those columns.

  ![data_format](https://user-images.githubusercontent.com/112113327/212549082-42b1d2c4-89bc-4a0d-8056-816e72c0dae1.png)

