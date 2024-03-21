![imges](images/5._Host_a_Dynamic_Web_App_on_AWS_with_Kubernetes_and_Amazon_EKS.gif)

![images](images/VPC.png)

The VPC is going to hold all of our resources, the first thing we are going to do is select our Region on the upper right hand corner select the reegion where you want create your VPC (us-east-1)

![images](images/Screenshot_1.png)

![images](images/Screenshot_2.png)

Now that we have created the VPC, the next thing todo is to enable the DNS hostname in the VPC, this simplifies the process of managing and connection of resources in the 

![images](images/Screenshot_3.png)

![images](images/Screenshot_4.png)

CREATE INTERNET GATEWAY



![images](images/Screenshot_5.png)

![images](images/Screenshot_6.png)

Now that the Internet Gateway is created, it is time to attach it to our VPC

![images](images/Screenshot_7.png)

![images](images/Screenshot_8.png)

CREATE SUBNETS

![images](images/Screenshot_9.png)

![images](images/Screenshot_10.png)

NOW its time to enable the auto-assign IP on the Public Subnets

![images](images/Screenshot_11.png)

![images](images/Screenshot_12.png)

Create Route Table for Public Subnets to have internet

![images](images/Screenshot_13.png)

![images](images/Screenshot_14.png)

![images](images/Screenshot_15.png)

![images](images/Screenshot_16.png)

SUBNET ASSOCIATION

![images](images/Screenshot_17.png)

![images](images/Screenshot_18.png)

CREATING NAT GATEWAYS

Nat Gateway allows resources in the Private Subnte in the VPC to have internet, For high availaility and fault tolerance we will create 2 Nat Gateways. But in this case we wil create 1 Nat Gateway to save costs and we will associate all our Private Subnets with the Nat Gateway.

![images](images/Screenshot_19.png)

![images](images/Screenshot_20.png)

Setting Up Private Subnets Route Table

![images](images/Screenshot_21.png)

![images](images/Screenshot_22.png)

Asoociate all the private subnest with the route table

![images](images/Screenshot_23.png)

Security Groups

1. Will be attached to the EC2 instnace connect end-point - port 22
2. Attach to the EC2 instance we will use to migrate data to RDS - PORT 22
3. RDS instance security group - port 3306

![images](images/Screenshot_24.png)

![images](images/Screenshot_25.png)

CREATE ENDPOINT

![images](images/Screenshot_26.png)

![images](images/Screenshot_27.png)

AMAZON RDS SUBNETS

![images](images/Screenshot_28.png)

![images](images/Screenshot_29.png)

AMAZON RDS

![images](images/Screenshot_30.png)

![images](images/Screenshot_31.png)

![images](images/Screenshot_32.png)

![images](images/Screenshot_33.png)

![images](images/Screenshot_34.png)

![images](images/Screenshot_35.png)

![images](images/Screenshot_36.png)

## Docker


![images](images/Screenshot_38.png)

![images](images/Screenshot_40.png)

![images](images/Screenshot_41.png)

![images](images/Screenshot_42.png)

![images](images/Screenshot_43.png)


![images](images/Screenshot_45.png)


### Building and Pushing Docker Image to ECR

![images](images/Screenshot_46.png)

![images](images/Screenshot_47.png)

![images](images/Screenshot_48.png)

![images](images/Screenshot_49.png)

![images](images/Screenshot_50.png)

![images](images/Screenshot_51.png)

![images](images/Screenshot_52.png)



S3 Bucket Setup and SQL Script Upload

![images](images/Screenshot_53.png)

![images](images/Screenshot_52.png)


Upload SQL script to S3 bucket

![images](images/Screenshot_53.png)

![images](images/Screenshot_54.png)

![images](images/Screenshot_55.png)



Create IAM Role with S3 Access

![images](images/Screenshot_56.png)

![images](images/Screenshot_57.png)

![images](images/Screenshot_58.png)

Next Launch an EC2 Instance in the Private App Subnet

We use this instance to migrate our data to RDS

![images](images/Screenshot_58.png)

![images](images/Screenshot_59.png)

![images](images/Screenshot_60.png)

![images](images/Screenshot_61.png)

![images](images/Screenshot_62.png)

![images](images/Screenshot_63.png)

![images](images/Screenshot_65.png)

#### Data Migration to RDS

![images](images/Screenshot_66.png)

![images](images/Screenshot_65.png)

![images](images/Screenshot_66.png)

![images](images/Screenshot_67.png)

![images](images/Screenshot_68.png)

![images](images/Screenshot_69.png)

#### EC2 Instance Termination

![images](images/Screenshot_70.png)

![images](images/Screenshot_71.png)


### Install kubectl, eksctl, and Helm

![images](images/Screenshot_72.png)

![images](images/Screenshot_73.png)


### Create a Secret in Secret Manager

Add all the envirnoment variables in our dockerfile as secrets in the aws secretes manager

![images](images/Screenshot_74.png)

![images](images/Screenshot_75.png)

![images](images/Screenshot_76.png)

Now lets enable the EKS Cluster to retrive the secret we stored, we create an IAM policy

![images](images/Screenshot_77.png)

![images](images/Screenshot_78.png)

![images](images/Screenshot_79.png)

![images](images/Screenshot_80.png)



EKS Cluster IAM Role Creation

Before we create an EKS cluster, we first have to create an IAM role for the cluster https://docs.aws.amazon.com/eks/latest/userguide/service_IAM_role.html#create-service-role


![images](images/Screenshot_81.png)

![images](images/Screenshot_82.png)

![images](images/Screenshot_83.png)

![images](images/Screenshot_84.png)

![images](images/Screenshot_85.png)

![images](images/Screenshot_86.png)

![images](images/Screenshot_87.png)

![images](images/Screenshot_88.png)

![images](images/Screenshot_89.png)

![images](images/Screenshot_90.png)




























