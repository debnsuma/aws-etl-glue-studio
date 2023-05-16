# Building an ETL job using Spark and Ray on AWS using AWS Glue  

## Create an Amazon S3 bucket 

Create an Amazon S3 bucket and copy the sample_dataset `data-engg-demo`

## Download the dataset to S3 

Copy the data set to the S3 bucket 

```bash
BUCKET_NAME='s3://data-engg-demo/dataset/covid-data/input/'

aws s3 cp --recursive sample_dataset/ $BUCKET_NAME

```
## Create a Glue Crawler 

Open the console and click on `Data Catalog` -> `Crawler`

![img1](/img/img1.png)

Click on `Add a data source` and add the S3 location of the dataset (JSON) 

![img1](/img/img2.png)

Add the bucket location `s3://data-engg-demo/dataset/covid-data/input/json` 

![img1](/img/img3.png)

Provide the IAM role, so that Glue can read the data from Amazon S3 

![img1](/img/img4.png)

Mention the Database you want to select and add a prefix 

![img1](/img/img5.png)

Once this is done just review all the parameters, click on `Create` and `Run` the Crawler.

![img1](/img/img6.png)

## Create an ETL job using the Glue Studio Visual Interface

We can now create an intractive Glue Studio Notebook. Go to the Glue console and go to `Data Integration and ETL` -> `AWS Glue Studio` -> `Job` and then click on `Visual with a blank canvas` and click on `Create` 

![img1](/img/img7.png)

And now you can follow this [workshop](https://pages.awscloud.com/anz-developer-webinar-data-analytics.html)



