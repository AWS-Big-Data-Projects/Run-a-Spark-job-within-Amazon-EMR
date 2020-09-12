# Run-a-Spark-job-within-Amazon-EMR

![image](https://user-images.githubusercontent.com/48589838/77054629-0251ad80-69f6-11ea-8d55-29b0d8b98842.png)         ![image](https://user-images.githubusercontent.com/48589838/77054833-2c0ad480-69f6-11ea-9855-0bdeec8535b7.png)


AWS and Amazon EMR
AWS is one of the most used cloud services platform, a lot of services are available, it is very well documented and easy to use.

A cloud services platform allow users to access on-demand resources (compute power, memory, storage) and services (databases, monitoring, workflow, etc.) via the internet with pay-as-you-go pricing.

Among all the cool services offered by AWS, we will only use two of them :

Simple Storage Service (S3), a massively scalable object storage service

Elastic MapReduce (EMR), a managed cluster platform that simplifies running big data frameworks, such as Apache Hadoop and Apache Spark. 

It can be view like Hadoop-as-a-Service, you start a cluster with the number of nodes you want, run any job you want and only pay for the time the cluster is actually up.

## The input and output files will be store using S3 storage.

## Create an Amazon S3 Bucket

Open the Amazon S3 console

Choose Create bucket

Type a name for your bucket (ex : my-first-emr-bucket) and choose its AWS Region then click next.

On the Set properties page, you can configure some properties for the bucket. In this tutorial we don’t need any specific properties, click next.

On the Set permissions page, you manage permissions that are set on the bucket that you are creating. We will use the default permissions, click next.

On the Review page, verify the settings and choose Create bucket.


## Upload files on Amazon S3

On the Amazon S3 console click on the bucket you just created

Choose Create folder, enter the name of the folder (ex : tutorialEMR), the encryption setting (ex : None) and save

Click on the folder you just created, then choose upload to upload the Spark application jar and the input text file on which you want to apply the wordcount

## Create an Amazon EMR cluster & Submit the Spark Job

Open the Amazon EMR console
On the right left corner, change the region on which you want to deploy the cluster
Choose Create cluster

On the General Configuration section, enter the cluster name, choose the S3 bucket you created (the logs will be stored in this bucket) and check Step execution.

On the Add steps section, select Spark application, click Configure and fill the popup box.

On the Software Configuration section, use the default release (the last one)

On the Hardware configuration section, choose the instance type and the number of instances

On the Security and access section, use the Default values.
Click on Create cluster
Click on the refresh icon to see the status passing from Starting to Running to Terminating — All steps completed

Now go back to the S3 console and you will see the output directory in which the result has been stored, you can click on it and download its contents.

special mention 

Robin JEAN

https://medium.com/big-data-on-amazon-elastic-mapreduce/run-a-spark-job-within-amazon-emr-in-15-minutes-68b02af1ae16
