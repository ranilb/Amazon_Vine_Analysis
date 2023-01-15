# Amazon Vine Analysis
In this project, we analyze Amazon reviews written by members of the paid Amazon Vine program to determine if there is any bias toward favorable reviews from Vine members in a selected dataset. The data set contains reviews of a specific product, from clothing apparel to wireless products. First, PySpark was used  to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Then PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset.

### The data
The [Toys data set](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Toys_v1_00.tsv.gz) was obtained from the [Amazon review datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt). The selected data set has 15 columns ans the following images shows the information about those columns.

  ![data_format](https://user-images.githubusercontent.com/112113327/212549082-42b1d2c4-89bc-4a0d-8056-816e72c0dae1.png)



## Deliverable 1: Perform ETL on Amazon Product Reviews
In this part, we created an AWS RDS database with tables in pgAdmin, and then the selected toys dataset from the Amazon Review datasets Links to an external site. and extract the dataset into a DataFrame. Finally, the DataFrame was transformed into four separate DataFrames that match the table schema in pgAdmin and uploaded the transformed data into the appropriate tables.

For example, the following pictures show the products dataframe in in google colab and the "products_table" in the pgAdmin.
#### Dataframe
![Screen Shot 2023-01-15 at 6 01 33 PM](https://user-images.githubusercontent.com/112113327/212572096-a753ae68-c164-447f-afae-a4bdd611386a.png) 

#### Table in pgAdmin
<img width="716" alt="Screen Shot 2023-01-15 at 5 35 40 PM" src="https://user-images.githubusercontent.com/112113327/212572132-c004a8fe-38d4-4e26-b791-1a417c23240a.png">


## Deliverable 2: Determine Bias of Vine Reviews 
This part is completed in "Vine_Review_Analysis.ipynb". 

## Deliverable 3:A Written Report on the Analysis
In the next step, we wanted to check if there is any bias toward favorable reviews from paid members in the dataset. First, the [Toys data set](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Toys_v1_00.tsv.gz) was transformed to a dataframe using PySpark in a google Colab Notebook and followed the steps explained in the next section.

### Results
Considering meaningful reviews, the reviews with 20 or more than 20 votes were considered. To further filter the data, the ratio between the helpful reviews and the total reviews considered. Then the reviews with the ratio greater than 50% were condered for the analysis. After that, the reviews written by paid customers and the unpaid customers were seperated into two data frames as shown below.

#### vine reviews
![Screen Shot 2023-01-15 at 6 30 57 PM](https://user-images.githubusercontent.com/112113327/212573466-09711f4f-ba33-4fb1-abf2-b74115508548.png)

#### Not from vine reviews
![Screen Shot 2023-01-15 at 6 31 11 PM](https://user-images.githubusercontent.com/112113327/212573472-50d522f0-94f2-43ea-82e8-e29255fee23d.png)

To decide if there is any bias toward favorable reviews from paid members, total number of five-star reviews (432) and the totoal muber of reviews (1266) were computed for vine reviews and the results are shown below.

 ![Screen Shot 2023-01-15 at 6 38 14 PM](https://user-images.githubusercontent.com/112113327/212573812-1b8f7578-53b8-4b3c-bd1a-f46ffbff709b.png). 
 
 ![Screen Shot 2023-01-15 at 6 38 03 PM](https://user-images.githubusercontent.com/112113327/212573827-a5932806-6822-4b9c-a6b8-3bef26decc3b.png)

Then the paid five-star percentage was computed for vine reviews as shown in the following image.

![Screen Shot 2023-01-15 at 6 41 09 PM](https://user-images.githubusercontent.com/112113327/212573910-45043bd5-714b-4e06-a723-4870f6f90ea9.png)

**Therefore, the five-review percentage for the vine reviews is 34.12%**

Simillarly, total number of five-star reviews (30072) and the totoal muber of reviews (62283) were computed for unpaid reviews and the results are shown below:

![Screen Shot 2023-01-15 at 6 44 39 PM](https://user-images.githubusercontent.com/112113327/212574018-aa751bdd-5fe3-417f-89b0-ebfcc909f6dd.png)

![Screen Shot 2023-01-15 at 6 44 32 PM](https://user-images.githubusercontent.com/112113327/212574022-8628facb-674d-4fed-89ea-ed6c015f7813.png)

Then the five-star percentage was coputed forunpaid reviews as shown in the following image.

![Screen Shot 2023-01-15 at 6 44 49 PM](https://user-images.githubusercontent.com/112113327/212574053-189f1e0f-4b45-47c6-8039-451ea9cfdc7f.png)

**Therefore, the five-review percentage for the unpaid reviews is 48.21%**
