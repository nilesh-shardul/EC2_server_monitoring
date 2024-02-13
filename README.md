
# <u> Project Title : EC2 Server Monitoring </u>

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


## Objective 2 : Create and configure a CloudWatch alarm that sends an email notification to HCMonitor@HeavenClassics.com if the CPU utilization goes below the threshold of 3%, consecutively three times for five minutes

### Follow the below steps to create and configure alarm with the given email

### Step 1: Select EC2 instance, go to Actions->Monitor and troubleshoot->Manage CloudWatch alarms <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/f746b02e-b0f5-4795-8a32-dc2d0f38755f) <br> </br>

### Step 2: Select Create an alarm and write new topic name e.g., EC2_CPU_UTIL_BELOW_3_PER and configure the email id HCMonitor@HeavenClassics.com  later as given in below steps (Step 6) <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/65022c52-6f1c-46f3-b0f1-8e0b9352bdd5) 

<i> Note : you can write existing topic name here with email id HCMonitor@HeavenClassics.com configured </i> <br> </br>

### Step 3: Set Alarm thresholds i.e., if CPU Utilization goes below the threshold of 3%, consecutively 3 times for 5 minutes as shown below <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/ead98f1e-9beb-4b64-91d5-5dfacaaf4962) <br> </br>


### Step 4: Click on Create button <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/9c86497f-ff1e-4a54-b0b8-37ad21afb96e) <br> </br>

### Step 5: New alarm is created for the selected instance <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/eb9a32dc-2333-4560-a476-4349021850a8) <br> </br>

### Step 6: Now as discussed in above slides if you have created new SNS topic you need to configure given email id (HCMonitor@HeavenClassics.com). For the same, go to SNS service  <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/3b6e14cc-a7ad-481f-bef4-94279eef7121) <br> </br>


### Step 7: Select the topic you have created. We have created topic name EC2_CPU_UTIL_BELOW_3_PER in earlier steps <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/726a4896-1a3c-4fcf-a401-06656985cf4d) <br> </br>


### Step 8: Click on Create Subscription button <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/9f4ead97-1489-40e0-9d99-6ff0fdf43290) <br> </br>


### Step 9: Add email id - HCMonitor@HeavenClassics.com in the endpoint field <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/17ca9c59-3084-4563-a38f-f4e95f969e3c) <br> </br>


### Step 10: Click on Create Subscription button. Status will be changed from Pending confirmation to Confirmed once the user accept the subscription after receiving the email.  <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/4c36f790-cd00-4bb6-b20b-b0e3e8c7eadf)

<i> Note : The step(confirming subscription) is necessary for the user to receive the emails set in alarm. </i> <br> </br>





## Objective 3 : Create an IAM group named Administrator Group and attach the full administrator access policy to the group <br> </br>

### First create new user group in IAM and then attach AdministratorAccess policy to the group as per the given steps below <br> </br>

### Step 1: Go to IAM > User groups <br> </br> 

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/b5fc3fa6-306e-4c7e-9648-4b3e0f7d8fa9) <br> </br>

### Step 2: Click on Create user group. Write group name e.g., Administrator_Group <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/2a24bc90-f690-4ee0-ab6e-28f2d9322886) <br> </br>


### Step 3: Scroll below to Attach permissions policies and check on AdministratorAccess under Policy name <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/b1213b51-649a-4b00-b639-247c169702dc) <br> </br>


### Step 4: Click on Create group button. The new group Administrator_Group will be created and listed as below <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/36cd6338-2c3a-4478-852f-b79b4c92868d) <br> </br>




## Objective 4 : Create a user for an employee of the company who requires administrator access to the company's AWS account, and then add the user to the Administrator Group. <br> </br>

### First create new user in IAM and add the user in Administrator Group as per the given steps below <br> </br>

### Step 1: Go to IAM > Users <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/d5debd75-125f-4046-acad-3d57ce026071) <br> </br>


### Step 2: Write username e.g., MyProject_Administrator_user_1 . As per requirement select -Programmatic access or Console access, password settings e.g., Autogenerate console password, allow user to create new password at first sign-in etc.<br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/ee0c94db-e502-4fa4-aa42-23bd146cfac9) <br> </br>


### Step 3: Add user to Administator_Group created before <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/0ad98be3-2358-4382-87b9-2cf3712a804c) <br> </br>


### Step 4: You can add few more properties in tags such as user type <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/381670c6-15dd-42f3-958c-294b80a193a1) <br> </br>


### Step 5: Review the settings and click on Create user button to create new user <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/66a995d0-1eb2-41a1-9db8-9aab8bf09924) <br> </br>


### Step 6: You will see success message and summary of new user created <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/7a9fddd1-de81-42c1-83ca-f54df1bc07a4) <br> </br>


### Step 7: New user can be seen under IAM > users <br> </br>

![image](https://github.com/nilesh-shardul/server_monitoring/assets/40804989/7927c85e-79ab-4ec9-845d-f94d0fbd3e12) <br> </br>


## Thank You !! ##



