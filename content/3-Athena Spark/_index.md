---
title : "Athena Spark"
date: 2024-01-01
weight : 3
chapter : false
pre : " <b> 3. </b> "
---
# Athena Spark
In this workshop, we will explore the features of Amazon Athena for Apache Spark and run hands-on labs that demonstrate features and best practices. By the end of the workshop, you will be able:

Create an Amazon Athena workgroup with Spark as the analytics engine
Create notebooks and run calculations in notebook
Use Cloudwatch logs for monitoring and debugging

[Amazon Athena for Apache Spark](https://aws.amazon.com/athena/spark/)  provides interractive analytics under a second to analyze petabytes of data using open source spark framework.Interactive Spark applications start instantly and run faster with our optimized Spark runtime, so you spend more time on insights, not waiting for results. Build Spark applications using the expressiveness of Python with a simplified notebook experience in an Athena console or through Athena APIs. With the Athena serverless, fully managed model, there are no resources to manage, provision, and configure and no minimum fee or setup cost. You only pay for the queries that you run.

Knowledge of [Spark](https://spark.apache.org/) , Python/Scala are useful but not a pre-requisite for this workshop

   - You download [Notebook](/files/athena_spark.ipynb)
### Create Spark workgroup and Notebook
   - Access the Athena Notebook console

   ![Image](/images/3/301.png?featherlight=false&width=90pc)
   - Create Spark workgroup

   ![Image](/images/3/302.png?featherlight=false&width=90pc)

   ![Image](/images/3/303.png?featherlight=false&width=90pc)

### Update IAM role of Athena Spark
   - Access the [IAM console](https://us-east-1.console.aws.amazon.com/iam/home?region=us-east-1#/home).
   - On the left navigation bar, select **Roles**
   - Choose Role was created by Athena
   - Add all permission we need

   ![Image](/images/3/304.png?featherlight=false&width=90pc)

### Execute Notebook
1. Import Notebook:
    - Access the [Notebook explorer](https://us-east-1.console.aws.amazon.com/athena/home?region=us-east-1#/notebook-explorer).
    - Choose **Import file**
    - Upload your notebook
2. Start query in notebook
   - Get Dataframe from glue data catalog
   
   ![Image](/images/3/305.png?featherlight=false&width=90pc)
   
3. Data preparation and exploration
   
   In this Lab we will show how to use Amazon Athena for Apache Spark to interactively run data analytics and exploration without the need to plan for, configure, or manage resources.

   - Write to S3 bucket

   ![Image](/images/3/306.png?featherlight=false&width=90pc)

   
   ![Image](/images/3/307.png?featherlight=false&width=90pc)

   - Analyze data from Government

   ![Image](/images/3/308.png?featherlight=false&width=90pc)
   - Create table in glue data catalog so we can also query data using Athena Query Editor.

   ![Image](/images/3/309.png?featherlight=false&width=90pc)


4. Build Visualizations

In this lab we will show how to build visualization in Amazon Athena for Apache Spark using Matplotlib and Seaborn.

[Matplotlib](https://matplotlib.org/)  is a comprehensive library for creating static, animated, and interactive visualizations in Python. Matplotlib helps to

* Create [publication quality plots](https://ieeexplore.ieee.org/document/4160265/citations?tabFilter=papers#citations) .
* Make [interactive figures](https://matplotlib.org/stable/api/figure_api.html#matplotlib.figure.Figure.savefig)  that can zoom, pan, update.
* Customize [visual style](https://matplotlib.org/stable/gallery/style_sheets/style_sheets_reference.html)  and [layout](https://matplotlib.org/stable/users/explain/axes/mosaic.html) .
* Export to [many file formats](https://matplotlib.org/stable/api/figure_api.html#matplotlib.figure.Figure.savefig) .
* Embed in [JupyterLab and Graphical User Interfaces](https://matplotlib.org/stable/gallery/#embedding-matplotlib-in-graphical-user-interfaces) .
* Use a rich array of [third-party packages](https://matplotlib.org/mpl-third-party/)  built on Matplotlib.

[Seaborn](https://seaborn.pydata.org/tutorial/introduction)  is a library for making statistical graphics in Python. It builds on top of [matplotlib](https://matplotlib.org/)  and integrates closely with [pandas](https://pandas.pydata.org/) data structures.

   - Use Seaborn to build visualization on this data

   ![Image](/images/3/310.png?featherlight=false&width=90pc)
   - Build visualization using Matplotlib

   ![Image](/images/3/311.png?featherlight=false&width=90pc)

5. Installing Additional Python Libraries
In this lab we will show how to import additional Python libraries to Amazon Athena for Apache Spark. We will use pip command to download a Python .zip file of the [bpabel/piglatin](https://github.com/bpabel/piglatin)  project from the [Python Package Index PyP](https://pypi.org/)I .

   - Access the [AWS Cloud9](https://us-east-1.console.aws.amazon.com/cloud9control/home?region=us-east-1#/product).
   - Access your environment

   ![Image](/images/3/312.png?featherlight=false&width=90pc)

   ![Image](/images/3/313.png?featherlight=false&width=90pc)

   ```shell
   mkdir testpiglatin
   cd testpiglatin
   virtualenv
   ```

   ![Image](/images/3/314.png?featherlight=false&width=90pc)
   - Create a subdirectory named unpacked to hold the project and Use the pip command to install the project into the unpacked directory
   ```shell
   mkdir unpacked
   pip install -t $PWD/unpacked piglatin
   ```

   ![Image](/images/3/315.png?featherlight=false&width=90pc)

   - Change to the unpacked directory and display the contents.
   ```shell
   cd unpacked
   ls
   ```
   ![Image](/images/3/316.png?featherlight=false&width=90pc)
   - Use the zip command to place the contents of the piglatin project into a file called library.zip, this will will be created under testpiglatin directory.
   ```shell
   zip -r9 ../library.zip *
   ```
   
   ![Image](/images/3/317.png?featherlight=false&width=90pc)
   - Copy the library.zip file into Amazon S3 bucket created in your AWS Account, replace the account-id with your AWS Account ID
   ```shell
   cd ..
   ls
   aws s3 cp library.zip s3://athena-spark-workshop
   ```
  
   ![Image](/images/3/318.png?featherlight=false&width=90pc) 

   ![Image](/images/3/319.png?featherlight=false&width=90pc) 

   - Execute notebook
   - 
   ![Image](/images/3/320.png?featherlight=false&width=90pc) 

6. Exploring Session Details

In this lab we will show how to explore Athena runtime session history and it's calculation details including when the session started and how many DPU ( Data Processing Units) it consumed and list of calculations it executed along with total runtime etc. There are two ways you can explore session details, one using **Notebook explorer** and another one using **Workgroup**

#### Using Notebook Explorer

- Click on Notebook explorer on the side menu and select the notebook you imported and click Session history from the Actions dropdown. This will display list of sessions crated for this notebook.

   ![Image](/images/3/321.png?featherlight=false&width=90pc) 

   ![Image](/images/3/322.png?featherlight=false&width=90pc) 

- Click on one of the Session ID to see the details, this will show you when the session started, session status and list of calculations it executed from the notebook along with total runtime it took to complete the calculation and status whether it **Completed** or **Failed**.

   ![Image](/images/3/323.png?featherlight=false&width=90pc)


- Click on one of the calculation to further to explore what notebook cell executed, total runtime duration, code it executed and result etc, you can also download the result from the **Results** tab.
 
   ![Image](/images/3/324.png?featherlight=false&width=90pc)


#### Using Workgroups

- Click on **Workgroups** under Administration menu

   ![Image](/images/3/325.png?featherlight=false&width=90pc)


- Click on one of the workgroup you crated for Spark where **Analytics engine** says **PySpark engine version 3**, it will show following Workgroup details which includes list of Notebooks and Sessions associated with this workgroup.

   ![Image](/images/3/327.png?featherlight=false&width=90pc)


- Click on **Session** tab and filter out sessions based on their status like **Active, Idle, Terminated** etc. You can further explore the session and calculation details by clicking on one of the session from the list.

   ![Image](/images/3/328.png?featherlight=false&width=90pc)