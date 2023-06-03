# AWS-customing EC2 instance for web-instance



1.	Create a web instance
2.	Create an internet gateway and attach it to VPC
3.	Create a subnet and a route table

Step 1: Creating a Custom VPC and enabling DNS hostname:

1.1	In the AWS management console, search for VPC:    
![image](https://github.com/ivybabes20/AWS-web-instance/assets/135469282/d82fccc3-e0c0-48c8-9a4a-7e6202da33d8)

1.2	Enter the name, and select the options shown below: 
 ![image](https://github.com/ivybabes20/AWS-web-instance/assets/135469282/7375a72b-7783-4240-810e-e6da1acb5d9c)

  
1.3	Click on Create VPC:
  ![image](https://github.com/ivybabes20/AWS-web-instance/assets/135469282/e7040b0e-6297-412e-9b4f-4dedc53e6a4d)


1.4	Select Users VPC, click on Actions, and then select Edit DNS hostname.
 
![image](https://github.com/ivybabes20/AWS-web-instance/assets/135469282/727244b5-8fdb-4475-979a-9b73e3036f36)

1.5	Click on Enable and Save changes.
![image](https://github.com/ivybabes20/AWS-web-instance/assets/135469282/0d662fde-7c33-4b7a-bdae-4b9abb2c23b0)

  ![image](https://github.com/ivybabes20/AWS-web-instance/assets/135469282/116f8624-fd22-428c-958c-35ef659892b6)



Step 2: Create an internet gateway and attach it to VPC:	

2.1	In EC2 console, click on Internet gateways, enter the name and click on Create internet gateway:
 ![image](https://github.com/ivybabes20/AWS-web-instance/assets/135469282/3df91dd4-7599-447d-bd40-daf7b228dca1)

2.2	Select the users’ internet gateway, click on Actions, and select Attach to VPC:
  

2.3	Select user VPC and click on Attach internet gateway:
  
 















Step 3: Create a subnet and a route table:
3.1	Click on the Subnets and then click on Create subnet:
 


3.2	Select users VPC, and click on Create subnet:
 


3.3	Enter the name, and select the Availability Zone:
 

3.4	Copy IPv4 CIDRs, paste them into IPv4 CIDRs Block, and click on Create subnet:
 
 


3.5	Select users subnet, click on Actions, and select Edit subnet settings:
 

3.6	Enable auto-assign public IPv4 address under Edit subnet settings:
  








3.7	Click on Create route table:
  

3.8	Select user VPC and click on Create route table below:
 



3.9	Select the users’ route table, click on Actions, and Select Edit routes:
 

3.10	Click on Add route:
 





3.11	Select Internet Gateway:
 


3.12	After selecting Internet Gateway, select the gateway you created, and click on save changes:
 




 


3.13	Click on created subnet association and click in Edit subnet associations:
















3.14	Select users subnet and click on Save associations:
 
 
















Part – 4 Launch EC2 instance:
4.1	Navigate to EC2 in the console, click on Instance, click on launch, and enter the name for the instance:
  

4.2	Click on Amazon Linux:
 


4.3	Select the t2.micro option:
 

4.4	Create a key pair:
 







4.5	Click on Network settings and select your VPC:
 

4.6	Select users custom subnet:
 








4.7	Select the inbound rules, and add HTTP and HTTPS rules:
 

4.8	Click on Advanced details, enter the code in User data, and click on Launch instance:
 






4.9	Click on launch instance:

 

4.10	Select the instance created and copy the IPv4 address in the instance, and paste it in a browser:
 


