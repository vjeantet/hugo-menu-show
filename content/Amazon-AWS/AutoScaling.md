+++
date = "2015-07-15T22:17:00+02:00"
draft = false
title = "Auto Scaling"

[menu.main]
Name = "Auto Scaling"
parent = "Amazon-AWS"
+++


AutoScaling allow you to automatically add or remove your EC2 instances according to your defined condition. To setup autoscaling we create autoscaling group and defined launch configuration for that group so, whenever any instance added in to group it will use that launch configuration .

Following are the step to setup auto scaling on AWS

1. Create AMI of EC2 instance

AMI (Amazon Machine Image) is used while new instance is created automatically. We define unique AMI id (e.g ami-xxxxxxxx) in launch configuration.

Following is the first step to create AMI (there is alternative option also).

create-aim-1
First step to create AMI
In next step it will ask for Image Name, description and other options. Please use help for more info.

create-aim-2
Final step to create AMI
After clicking Create Image button, It will start create image process and give you unique AMI id something like ami-xxxxxxxx that will required in create launch configuration. It will take time to create image depend on the size of your EBS.

2. Create launch configuration

This is the required step to setup autoscaling. As name state, Launch configuration is used when any instance is added to autoscaling group. There are some required field like launch-configuration-name, image-id, instance-type, key, security-groups.

Lets create launch configuration.

Step 1 : Go to Launch Config Page and Start Create Launch configuration

create-new-launch-configuration-1
Step 1 : Go to Launch Config Page and Start Create Launch configuration
Step 2 : Select AMI

create-new-launch-configuration-2
Step 2 : Select AMI
OR you select existing EMI if you are already created

create-new-launch-configuration-3
Step 2 : Choose Existing AMI
Step 3 : Choose Instance Type

create-new-launch-configuration-4
Step 3: Choose Instance Type
Step 4 : Name launch configuration & other info

create-new-launch-configuration-5
Step 4: Name launch configuration & other info
Step 5 : Choose Storage

create-new-launch-configuration-6
Step 5: Choose Storage
Step 6 : Choose Security Group

create-new-launch-configuration-7
Step 6: Choose Security Group
Step 7 : Review

create-new-launch-configuration-8
Step 7: Review
Step 8 : Choose Key pair

create-new-launch-configuration-9
Step 8: Choose Key pair
If you are use cli then type following command to create launch config

aws autoscaling create-launch-configuration --launch-configuration-name aws-as-conf --image-id ami-xxxxxxxx --instance-type m1.large --key myPrivate --security-groups mySecurityGroup

To List all launch configuration

aws autoscaling describe-launch-configurations

3. Create Autoscaling Group

Autoscaling group use launch configuration to create instance and add it into group. There are some require parameters like availability-zones, min/max-size, load-balancer-names, health-check-type etc

@TODO : UI Steps

If you are use cli then type following command to 

aws autoscaling create-auto-scaling-group --auto-scaling-group-name test-autoscal-group --launch-configuration aws-as-conf --availability-zones us-east-1a us-east-1b --min-size 1 --max-size 5 --load-balancer-names test-lb --health-check-type ELB --health-check-grace-period 300 --tag "k=Name, v=Test AS, p=true"

Add instance policy :

aws autoscaling put-scaling-policy --auto-scaling-group-name test-autoscal-group --policy-name test-as-add-one --scaling-adjustment 1 --adjustment-type ChangeInCapacity

Remove instance policy :

aws autoscaling put-scaling-policy --auto-scaling-group-name test-autoscal-group --policy-name test-as-remove-one --scaling-adjustment -1 --adjustment-type ChangeInCapacity

Creating Cloud watch alarms from UI

@TODO: UI steps

 

Table