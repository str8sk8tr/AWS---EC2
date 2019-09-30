https://aws.amazon.com/

### EC2 Instance - Install & configure Kali Linux

# Task:
Show how to Launch an AWS Linux EC2 Instance.

### Steps:
I went to AWS Management Console (AWS Services) → Clicked, SERVICES. Than selected, EC2 instance, from the menu → Clicked, LAUNCH INSTANCES. 

Step#1 (inside the console), Chose an instance, Amazon Machine Image (AMI). I than chose, Amazon Linux 2 (1 virtual CPU’s/1Memory Gigs of RAM) → Selected, CONFIGURE INSTANCE DETAILS.

•	Number of instances = 1

•	Network = Kept the default virtual server Amazon provided

•	Subnets = For availability zone, I chose US-east-1a

•	Auto-assign Public IP = I chose Disable (Hides my public IP address)

•	IAM role = None (I will create the server for Linux Commands myself)

•	Shutdown behavior – Selected, STOP. This is for in case the server shuts down by accident. I do not want it to delete when the server shuts down

•	Enable termination protection = I selected, Protect against accidental termination. This is a second layer protection to ensure I don’t accidently delete the server

•	Monitoring = Choose nothing. There is a fee for the service

•	Tenancy = I chose, dedicated – Run a Dedicated instance. Hardware will be dedicated only to me for now

Step#2 Network interfaces

•Left IP address assignment to Amazon default since I don’t want my IP address public.
(Chose, Add Storage → My default root Memory Gigs of RAM is: 8)

•	Volume type: Chose, General purpose SSD (GP2)

•	Delete on Termination = Unchecked it. To preserve volume if Root server is ever deleted

•	Encryption = Left it as Not encrypted

Step#3, Add Tags (Important for naming your server)

Step#4, Configure Security Group

•	Assign a security Group = Selected “Create a new security group”. Gave it a name  & description.

•	Assigned my Router’s public IP address. This is to avoid unwanted connections from everywhere. If you leave it as Amazon’s default, anyone can possibly connect to your server.

Step#5, Review Instance launch

Step#6, Click, launch when satisfied with your selections

Step#7, Select an existing key pair or create a new key pair
I chose, “Create a new key pair” since I don’t have an existing one → Name it → Click, download key pair (That downloaded a private key to my local machine). 
Afterwards, I got an error reading,"Launch Failed". I had to research why. I read through the documentations. But luckily, 30 minutes later, Amazon sent an e-mail apologizing for the delay on setting up the instance.

Step#7, launch the instance
Had to download PuTTY in order to connect the Linux server. PuTTy requires a PPK in order to work. After downloading PuTTY, you will need to convert your PEM file into PPK file from the key generator.

Step#8, logging in to instance
Openned up PuTTy → Copy your Public DNS name → Paste it in PuTTY under "Host Name (or IP Address)” → Keep Port 22 SSH → Under SSH, expand and then select off → than authenticate that you have connection by logging in. NOTE: First time users, you sign in by using, “ec2-user”.
