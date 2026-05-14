---
title : "Preparation"
date: 2024-01-01
weight : 2
chapter : false
pre : " <b> 2. </b> "
---
# Preparation

## IAM role general
We'll create a few general iam roles:
1. Access the IAM console:
    - Access the [IAM console](https://us-east-1.console.aws.amazon.com/iam/home?region=us-east-1#/home).
    - On the left navigation bar, select **Roles**
    - Select **Create role**.
2. Create role for Glue.
   - Select **AWS Service**.
   - Enter **Glue** in "Use case".
   - Select **Next**.
   - Add permission we need
   - Enter Role name
   - Select **Create role**.
   
   ![Image](/images/2/202.png?featherlight=false&width=90pc)
3. Similar with CloudFormation

    ![Image](/images/2/201.png?featherlight=false&width=90pc)

## Athena Spark
### CloudFormation Template
Before starting this workshop, you need to create the required AWS resources. To do this, we provide AWS CloudFormation template to create a stack that contains the resources. When you create the stack, AWS creates a number of resources in your account.


   - You download [CloudFormation Template](/files/template.json)
   - Access the [CloudFormation create console](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create?stackName=Athena-Spark-Workshop)
   - Choose **Upload a template file**
   - Upload template file( You can view Canvas mode in **View in Application Composer**)

   ![Image](/images/2/2031.png?featherlight=false&width=90pc)

   - Choose **Next**
   - Choose your CloudFormation role in Permission

   ![Image](/images/2/203.png?featherlight=false&width=90pc)
   - Choose your Stack failure options
   - Choose **Next**

   ![Image](/images/2/204.png?featherlight=false&width=90pc)
   - Enter your Stack name 
   - Choose **Next**

   - Choose **Submit**

   ![Image](/images/2/205.png?featherlight=false&width=90pc)

   ![Image](/images/2/2051.png?featherlight=false&width=90pc)

### Upload dataset & create table
1. Upload dataset:
   - You download dataset [Financial Sample](/files/Financial.csv)
   - Upload to your bucket created by CloudFormation with path: financial/Finacial.csv

   ![Image](/images/2/206.png?featherlight=false&width=90pc)

   ![Image](/images/2/207.png?featherlight=false&width=90pc)
2. Create Database, Table in Glue Catalog
   - Access the [Glue Database console](https://us-east-1.console.aws.amazon.com/glue/home?region=us-east-1#/v2/data-catalog/databases)
   - Choose **Add database**
   - Enter database information

   ![Image](/images/2/208.png?featherlight=false&width=90pc)

   - Access the Glue Crawler console
   - Choose **Add Crawler**
   - Enter crawler information

   ![Image](/images/2/209.png?featherlight=false&width=90pc)

   - Choose your crawler
   - Choose **run**
   ![Image](/images/2/210.png?featherlight=false&width=90pc)

3. Check data in Athena
   - Access the [Athena console](https://us-east-1.console.aws.amazon.com/athena/home?region=us-east-1#/query-editor)
   - Test query in your table & dataset

     ![Image](/images/2/211.png?featherlight=false&width=90pc)

## Athena Federation
### RDS 
   - Access the [RDS databases](https://us-east-1.console.aws.amazon.com/rds/home?region=us-east-1#databases:)
   - Choose **Create Database**
   - In this part you can use default VPC
   
     ![Image](/images/2/212.png?featherlight=false&width=90pc)
 
     ![Image](/images/2/213.png?featherlight=false&width=90pc)

     ![Image](/images/2/214.png?featherlight=false&width=90pc)
   - Secret when you use Secret Manager

     ![Image](/images/2/215.png?featherlight=false&width=90pc)