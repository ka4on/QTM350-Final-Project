# QTM350-Final-Project
## -- Performance of Deploying Textract on Rotated Images and Handwritten text.

### Amazon Textract
[Amazon Textract](https://aws.amazon.com/cn/textract/) is a machine learning (ML) service on [AWS](https://aws.amazon.com/) that uses OCR to automatically extract text, handwriting, and data from scanned documents such as PDFs. To get started using Amazon Textract on AWS, follow the instructions [here](https://docs.aws.amazon.com/textract/latest/dg/getting-started.html).

### Introduction
This project focuses on testing the performance of deploying Textract in various situations. We test the service on rotated images, handwritten names, as well as documents written in languages other than English. To look at our project follow the [link](https://webpage-final-kz.s3.amazonaws.com/final.html).

### Architecture Overview
![archi](https://webpage-kairan.s3.amazonaws.com/archi.jpg)

The diagram illustrates the overall outline of what AWS services were utilized in this architecture. 
The user first uploads the document using the Amazon Simple Storage Service (S3). Once the document is in the web bucket, it could then be accessed by Amazon SageMaker, the primary tool to train and deploy machine learning models in AWS. Through the Jupyter notebook hosted within the EC2 T3 instance, the user uses the command line interface to pass the data to Amazon Textract. Upon extraction, the text is transformed and stored once again for the user to view.

### Sample Code for Using Textract
To get started with Textract, you need first follow the instructions [here](https://docs.aws.amazon.com/textract/latest/dg/setting-up.html) to set up the environment for running Textract on your AWS. Then for deploying the service you could use [AWS SageMaker](https://aws.amazon.com/cn/sagemaker/), initiate a notebook instance, then use the juypter notebook in it. 

One last thing before you try out the code is to upload an image or document that you want to process on an AWS S3 Bucket. For information of creating bucket and uploads files, click [here](https://docs.aws.amazon.com/AmazonS3/latest/userguide/GetStartedWithS3.html). 

A sample code for using Textract to detect texts is as following:
```
!aws textract detect-document-text --document '{"S3Object":{"Bucket":"bucket","Name":"document"}}
```
you will get a json output that contains the detected word, texttype, and confidence level. You can see the json output in the project [link](https://webpage-final-kz.s3.amazonaws.com/final.html).
Now if you use Python SDK for deploying Textract. Here are some codes that will come handy. First import AWS SDK for Python(Boto3)
```
import boto3
```
Next, we create an instance `client` of the client object in the `boto3` package for `textract`. It will allow use to communicate and make requests to the Textract service using Python. 
```
textract=boto3.client('textract')
```




