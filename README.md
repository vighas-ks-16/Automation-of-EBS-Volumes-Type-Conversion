# Automation-of-EBS-Volumes-Type-Conversion
Type Conversion of EBS Volumes : gp2 to gp3


### PROJECT DESCRIPTION :

It is the responsibility of the Cloud Engineer to take care of the AWS Environment and make sure it is in compliance with the organizational policies.

AWS CloudWatch is used in combination with AWS Lambda to govern the resources according to the compliance policies of the organization.

A Lambda Function is triggered when an Amazon Elastic Block Store (EBS) Volume is created.

CloudWatch Events is used to monitor and respond to the EBS Volumes that are of type gp2 and convert them into type gp3.


### PROJECT WORKFLOW :

### Defining the Lambda Function :


![WhatsApp Image 2024-06-19 at 10 30 25_138e04d4](https://github.com/vighas-ks-16/Automation-of-EBS-Volumes-Type-Conversion/assets/107311113/3de86493-a960-420d-ad47-b0c68bbbe87e)



This Python script, designed for an AWS Lambda function, modifies the type of an Amazon EBS volume to 'gp3'. 

The get_volume_id_from_arn function extracts the volume ID from the provided Amazon Resource Name (ARN) by splitting the ARN string. 

In the lambda_handler function, the volume ARN is obtained from the event, and the volume ID is extracted using the get_volume_id_from_arn function. 

The boto3 library's EC2 client is then used to call modify_volume, which updates the volume type to 'gp3'. 

This function is triggered by an event containing the ARN of the EBS volume to be modified.


### Setting up the Amazon EventBridge Rules :

![WhatsApp Image 2024-06-19 at 10 34 51_9fb65fcd](https://github.com/vighas-ks-16/Automation-of-EBS-Volumes-Type-Conversion/assets/107311113/62025022-d83d-47ab-94ac-2b2d9e59fe0b)


![WhatsApp Image 2024-06-19 at 10 34 52_2636e960](https://github.com/vighas-ks-16/Automation-of-EBS-Volumes-Type-Conversion/assets/107311113/f89cf62f-8cab-4234-a610-d9fc3020856f)


### Defining an IAM Rule (Customer Managed) :

![WhatsApp Image 2024-06-19 at 10 35 29_cf292b0f](https://github.com/vighas-ks-16/Automation-of-EBS-Volumes-Type-Conversion/assets/107311113/f13b8ab8-7a12-4f2d-b276-5b1e7068b743)


### Making the Amazon EventBridge Rule to trigger the Lambda Function :

![WhatsApp Image 2024-06-19 at 10 35 29_bbe4b350](https://github.com/vighas-ks-16/Automation-of-EBS-Volumes-Type-Conversion/assets/107311113/9891ec64-9662-4a19-b504-4a60d04bbe73)


### Creating an EBS Volume of type gp2 :

![WhatsApp Image 2024-06-19 at 10 56 57_e74c353b](https://github.com/vighas-ks-16/Automation-of-EBS-Volumes-Type-Conversion/assets/107311113/f70b9596-b0d6-4a71-9168-ba82cfd2b56a)


### Upon refreshing the page, the EBS Volume gets converted to type gp3 :

![WhatsApp Image 2024-06-19 at 10 56 57_941fc503](https://github.com/vighas-ks-16/Automation-of-EBS-Volumes-Type-Conversion/assets/107311113/e7ac6f34-ed93-4c12-a90a-647f8154a310)






