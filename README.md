# AWS---Automation-with-python
Using python to automate services on AWS

Overview

This project incorporates EC2, lambda and eventbride, when an event occurs - this will trigger a lambda function and start/stop an ec2 instance.

![image](https://github.com/user-attachments/assets/78dbd0b4-e010-4848-b242-56d59223e4ee)
![image](https://github.com/user-attachments/assets/5228ddc4-a8a1-4639-9bab-83e51fdf5415)
![image](https://github.com/user-attachments/assets/8279c7dd-a48d-4878-b934-81f2b1c01151)


AWS Lambda -is a serverless compute service for running code without having to provision or manage services, you pay for only the compute time you consume, it is an event driven function.


EC2 - is a web services that allows users to 'rent' virtual computers or instances to run their applications in the cloud. EC2 offers a variety of instance sizes and configurations with different storage and networking resources.


AWS Eventbridge - simply put, simplifies creating, executing and managing millions of schedules across AWS services without provisioning or managing underlying infrastrcuture.







![image](https://github.com/user-attachments/assets/e3ae5487-c815-44b5-8e99-e53f5cae18c3)

![image](https://github.com/user-attachments/assets/9cb5da9d-b233-4866-b922-cb1a3fc49a55)


I needed a log group created for later in the project, so an empty log was run.
 

![image](https://github.com/user-attachments/assets/2de1497f-cee2-4ad8-aa42-ea839ab30b72)


Now we need to create an eventbridge rule, we will need a cloudtrail in place as i will be using the cloudtrail api 


![image](https://github.com/user-attachments/assets/bd262215-981c-4ca7-ba84-3f7c68107625)
![image](https://github.com/user-attachments/assets/ddf315a7-d846-4e1d-8d35-f9ae6da73ee9)


I then set up an eventbridge scheduler with Lambda and this is invoked asynchronously – eventbridge is a serverless service and connects application components together using events, eventbridge also has the capability to automatically ingest events from over 200 AWS services and third party SaaS partners.


![image](https://github.com/user-attachments/assets/d2574ddb-97ee-4716-bf8f-35e17c7aba52)
![image](https://github.com/user-attachments/assets/24954443-b8fe-41fc-ae47-45d934cd5f96)


I then needed to create a target when the rule is hit, in this case the lambda function created earlier.


![image](https://github.com/user-attachments/assets/940bdc24-e892-4ad5-9b37-9a717bbfee0d)


When I go back into lambda on the console you can see the trigger is set 


![image](https://github.com/user-attachments/assets/7cbaa558-ba36-4575-aaaa-4c0991f44a88)


Using boto3 documentation I imported the stop/start code for an ec2


![image](https://github.com/user-attachments/assets/10b8d0b2-a75a-4a71-b8bb-0eb29ee986e5)


Next I created an EC2 instance I kept it as amazon linux and used t2 micro as it came under the free tier
We can see that the cloudwatch log on the lambda function is working highlighted by the log at 20:18


![image](https://github.com/user-attachments/assets/f089749c-799c-43f7-9422-75c71a47184c)


I then selected the below and went to a JSON format editor


![image](https://github.com/user-attachments/assets/8a790494-3019-4d94-a023-681fb42e06dc)
![image](https://github.com/user-attachments/assets/ad2f16b2-8fe7-4917-ab67-ff764e4e0ecf)


Had to create permissions on IAM to allow the EC2 instance to tag, which can be seen below


![image](https://github.com/user-attachments/assets/ce98dbf3-a463-406d-8fe8-7ab1a04ab638)
![image](https://github.com/user-attachments/assets/cd3ec9ca-b4f8-4028-9f8f-ed8a6173e75a)
![image](https://github.com/user-attachments/assets/eb532b55-3937-4fce-bd64-ac933bf6f0a7)












