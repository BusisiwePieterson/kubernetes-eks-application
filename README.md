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













