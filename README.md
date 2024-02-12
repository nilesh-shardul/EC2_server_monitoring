
# Project Title : AWS Technical Essentials Project – Server Monitoring

Heaven Classics successfully creates an EC2 Server Instance for Windows 2012 Server. After launching the instance on the server, the next step was to monitor the operations.
Monitoring is important to keep an eye on the performance of an EC2 instance. It helps gather data from all parts and is useful for debugging failure.
The monitoring team at Heaven Classics started monitoring activities using the CloudWatch Service in the AWS Management Console. The Heaven Classics support team were required to meet the following objectives:

Check and observe the CPU utilization graph for the EC2 instance
Create and configure a CloudWatch alarm that sends an email notification to HCMonitor@HeavenClassics.com if the CPU utilization goes below the threshold of 3%, consecutively three times for five minutes
Create an IAM group named Administrator Group and attach the full administrator access policy to the group
Create a user for an employee of the company who requires administrator access to the company's AWS account, and then add the user to the Administrator Group.



## Objective 1 : Check and observe the CPU utilization graph for the EC2 instance <br> </br>

### Step 1: Go to EC2 Service and click on Launch Instance <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/92288af9-6d2c-4ee6-8651-c358dd73c2b4)  <br> </br> 


### Step 2: Select Amazon Linux 2 AMI as shown below  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/c4edf8b8-8a28-47c9-b45a-da0c2de438f9)  <br> </br> 


### Step 3: Select instance type as t2.micro and click on Review and Launch  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/5eed8664-011e-4842-93e8-31ab546ee18d)  <br> </br> 


### Step 4: Keep default values for VPC, Subnet, Security Group, Storage etc. and click on Edit tags  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/54159e39-b2bf-4334-a232-2312ff0fc64f)  <br> </br> 


### Step 5: Give instance name e.g., MyProject_instance_1 and click on Review and Launch button  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/8c71bc5d-4674-4b4a-ba5e-7e58ad151e61) <br> </br> 

### Step 6: Click on Launch button  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/0cf32233-085f-4fc5-becf-db438666fecd)  <br> </br> 


### Step 7: Create new keypair giving some name e.g., MyProject_keypair_1, download file on your machine and click on Launch instances button  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/6e5e73f5-b621-4f77-bda2-1f0afe532604)  <br> </br> 


### Step 8: Check if new instance is running   <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/3357807b-35ed-43ae-8e02-42a929b453c0)  <br> </br> 


### Step 9: Select the EC2 instance and click on Monitoring tab to see CPU utilization(%) from CloudWatch. You can select the duration in the Graph  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/a39b8baa-305a-4711-8d66-09c4da8cdb37)  <br> </br> 


### Step 10 :Type the name of dashboard e.g., MyProject_ec2_dashboard_1  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/05754793-ef14-499c-90d6-2d25a6a402cf)  <br> </br> 
 

### Step 11: Select Graph type as Line Graph as shown below  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/a75845b9-1599-4727-9a2b-a732e3adf455)  <br> </br> 


### Step 12: Click on Metrics as shown below  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/67e575a0-f6f5-4d90-b4d8-6f489d607ce5)  <br> </br> 


### Step 13: Select EC2 service as shown below  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/3824a3ad-cb7d-49a8-96e9-f4cd68f34c9a)  <br> </br> 


### Step 14: Select per-instance metrics as shown below  <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/1c4f51a0-637b-4705-b46a-88620cedb444)  <br> </br> 


### Step 15: Select Metric CPUUtilization and click on Create widget button <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/be1c54c7-e9f6-4543-837c-1452fe095db6)  <br> </br> 


### Step 16: After that you can see the Dashboard created ( in this project MyProject_ec2_dashboard_1 )    <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/2b827fa6-e3cf-4931-a4cb-053f38073d2b)  <br> </br> 



