# AWS-Serverless-Architecture-Assignment

## Assignment 1 – EC2 Auto Start/Stop using Tags
The objective of this assignment is to automate the starting and stopping of EC2 instances using AWS Lambda and Boto3, based on tags applied to the EC2 instances.
Two EC2 instances were created using the Amazon Linux AMI.
Instance Names:

SharmajiAuto-Stop-Instance

SharmajiAuto-Start-Instance
![Screenshot EC2 state change snapshot](https://github.com/user-attachments/assets/ed886c98-480a-4082-884c-a1f98adc49e6)

Tags added to identify what action should be performed by the Lambda function.
Instance Name	Tag Key	Tag Value
SharmajiAuto-Stop-Instance	Action	Auto-Stop
SharmajiAuto-Start-Instance	Action	Auto-Start

![EC2 Auto Start-Stop using Tags snapshot ](https://github.com/user-attachments/assets/43c4e0ff-1861-4d16-a74c-d4803eb2bf91)
![EC2 Auto Start-Stop using Tags snapshot2](https://github.com/user-attachments/assets/b8562f55-b434-4bf7-897c-71fab34105c2)

To be allow Lambda to manage EC2 instances, an IAM role has created
![Role permission snapshot](https://github.com/user-attachments/assets/453b8a6a-c872-4431-9df5-bd3a2bd5b79e)

Lambda Function Code added 
![Lambda function snapshot](https://github.com/user-attachments/assets/6e310e04-c9e4-4124-afc8-5976fd4080d0)
Lambda Function testing
![Lambda Execution result snapshot](https://github.com/user-attachments/assets/8840662a-d655-42d3-a509-28cedb60648b)

## EC2 dashboard showing updated instance states.
![Screenshot EC2 state change snapshot](https://github.com/user-attachments/assets/40d00f28-a67b-4928-8af5-8b212d84504b)

## Assignment 2: Automated S3 Bucket Cleanup (Delete Files Older Than 30 Days)

## Summary
The objective of this assignment is to automate the cleanup of an S3 bucket by deleting files that are older than 30 days using AWS Lambda and Boto3.

## Step 1: Create S3 Bucket
- Created an S3 bucket named:
  **sharmaji-s3-cleanup-bucket**
- Uploaded multiple test files into the bucket for cleanup testing.
- ![File inside bucket snapshot](https://github.com/user-attachments/assets/7ae7b4a5-9924-4228-ab25-b690c456dbe2)
- 
  ## Step 2: Create IAM Role for Lambda
- Created an IAM role named:
  **SharmajiLambdaS3CleanupRole**
- Attached policy:
  **AmazonS3FullAccess**
- This role allows Lambda to list and delete S3 objects.
  ![IAM role summary snasphot](https://github.com/user-attachments/assets/174dd9be-1b97-48b5-bae1-e712eee3fb56)
  ## Step 3: Create AWS Lambda Function
- Created a Lambda function named:
  **SharmajiS3CleanupLambda**
- Runtime used:
  **Python 3.x**
- Assigned execution role:
  **SharmajiLambdaS3CleanupRole**
  ![Lambda code deployed snapshot](https://github.com/user-attachments/assets/2935dc8e-9650-4e46-8d95-b2bd6a41899e)

  ## Step 4: Lambda Function Logic
The Lambda function performs the following actions:
1. Connects to S3 using Boto3.
2. Lists all objects in the specified bucket.
3. Calculates the date older than 30 days.
4. Deletes files older than 30 days.
5. Logs deleted file names for verification.
![Lambda configuration snapshot](https://github.com/user-attachments/assets/a50097c5-a7c7-406d-aa88-a533a86def04)

## Step 5: Testing the Lambda Function
- A test event was created in Lambda.
- Lambda function was manually triggered.
- Execution completed successfully without errors.
  ![Test execution logs snapshot](https://github.com/user-attachments/assets/8324ecea-34c3-4a14-b30b-952a8206b640)

  ## Step 6: Verification
- Verified the S3 bucket contents after Lambda execution.
- Older files were removed
  ![File inside bucket snapshot](https://github.com/user-attachments/assets/5fd75beb-5681-4d9c-a148-58aa1ad1ac29)
  ![S3 bucket (sharmaji-s3-cleanup-bucket) Snapshot](https://github.com/user-attachments/assets/c7423b63-190a-4b47-9e66-05488cf1ab13)

  ## Assignment-3 Detect Unencrypted S3 Buckets
   ## Summary
To identify Amazon S3 buckets that do not have server-side encryption enabled using AWS Lambda and Boto3.
## Step 1: S3 Bucket Setup
- Verified existing S3 buckets.
- Ensured at least one bucket had server-side encryption disabled.
  ![Bucket snapshot](https://github.com/user-attachments/assets/ebc8a2b3-7ab5-4b10-80fb-afc130798204)
  ## Step 2: IAM Role Creation
- Created IAM role:
  **SharmajiLambdaS3ReadOnlyRole**
- Attached policy:
  **AmazonS3ReadOnlyAccess**
  ![IAM role permission snapshot](https://github.com/user-attachments/assets/17fa4f27-e183-4f9c-a7b4-5df42b5bc4f8)
  ## Step 3: Lambda Function Setup
- Created Lambda function:
  **SharmajiDetectUnencryptedS3Lambda**
- Runtime: Python 3.x
- Assigned IAM role:
  **SharmajiLambdaS3ReadOnlyRole**
![Lambda configuration page snapshot](https://github.com/user-attachments/assets/ed502e40-68a0-4364-9cfa-ac1806162280)
## Step 5: Testing and Verification
- Lambda function was manually triggered.
- Logs confirmed detection of unencrypted buckets.
  ![Lambda code deployed snapshot](https://github.com/user-attachments/assets/55f17775-b3c9-41b3-8718-4e345f8000b0)
  ![CloudWatch logs output snapshot](https://github.com/user-attachments/assets/99512cce-e215-41cc-a2db-54cfbc9bf085)

  






  

  
















