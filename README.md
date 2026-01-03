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









