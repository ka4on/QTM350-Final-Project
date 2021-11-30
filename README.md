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
To get started with Textract, you need first follow the instructions [here](https://docs.aws.amazon.com/textract/latest/dg/setting-up.html) to set up the environment for running Textract on your AWS.
