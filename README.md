https://aws.amazon.com/console/ 

### EC2 Instance - Install & configure Kali Linux

# Task:
Show how to Launch an AWS Linux EC2 Instance.

### Steps: Go to AWS Management Console (AWS Services) → Clicked, SERVICES. Than selected, EC2 instances, from the menu → Clicked, LAUNCH INSTANCES in the dashboard.

Step 1: (inside the console), Chose an instance, Amazon Machine Image (AMI). I than chose, Amazon Linux 2 (1 virtual CPU’s/1Memory Gigs of RAM) → Selected, CONFIGURE INSTANCE DETAILS.

•	Number of instances = 1

•	Network = Kept the default virtual server Amazon provided

•	Subnets = For availability zone, I chose US-east-1a

•	Auto-assign Public IP = I chose Disable (Hides my public IP address)

•	IAM role = None (I will create the server for Linux Commands myself)

•	Shutdown behavior – Selected, STOP. This is for in case the server shuts down by accident. I do not want it to delete when the server shuts down

•	Enable termination protection = I selected, Protect against accidental termination. This is a second layer protection to ensure I don’t accidently delete the server

•	Monitoring = Choose nothing. There is a fee for the service

•	Tenancy = I chose, dedicated – Run a Dedicated instance. Hardware will be dedicated only to me for now

Step 2: Network interfaces

• Left IP address assignment to Amazon default since I don’t want my IP address public.
(Chose, Add Storage → My default root Memory Gigs of RAM is: 8)

•	Volume type: Chose, General purpose SSD (GP2)

•	Delete on Termination = Unchecked it. To preserve volume if Root server is ever deleted

•	Encryption = Left it as Not encrypted

Step 3: Add Tags (Important for naming your server)

Step 4: Configure Security Group

•	Assign a security Group = Selected “Create a new security group”. Gave it a name  & description.

•	Assigned my Router’s public IP address. This is to avoid unwanted connections from everywhere. If you leave it as Amazon’s default, anyone can possibly connect to your server.

Step 5: Review Instance launch

Step 6: Click, launch when satisfied with your selections

Step 7: Select an existing key pair or create a new key pair
- I chose, “Create a new key pair” since I don’t have an existing one → Name it → Click, download key pair (That downloaded a private key to my local machine). 
Afterwards, I got an error reading,"Launch Failed". I had to research why. I read through the documentations. But luckily, 30 minutes later, Amazon sent an e-mail apologizing for the delay on setting up the instance.

Step 8: launch the instance (connect SSH Protocol)
- Downloaded PuTTY in order to connect the Linux server. PuTTY requires a PPK in order to work. After downloading PuTTY, you will need to convert your PEM file into PPK file from the key generator.

Step 9: logging in to instance
 - Openned up PuTTY → Copy your Public DNS name → Paste it in PuTTY under "Host Name (or IP Address)” → Keep Port 22 SSH → Under SSH, expand and then select off → than authenticate that you have connection by logging in. NOTE: First time users, you sign in by using, “ec2-user”.


## Take NOTE:
Amazon’s abuse policy; do not allow you to scan the third party premises. In addition, to conduct pentesting you need to complete the Penetration testing request form.

### Documentation:

![Lauch instance#1](https://user-images.githubusercontent.com/28675258/67623218-c755a000-f7f0-11e9-92a8-d67a33d046ed.PNG)
![Lauch instance#2](https://user-images.githubusercontent.com/28675258/67623219-c755a000-f7f0-11e9-8939-e15dcaea92bb.PNG)
![Lauch instance#3 (Configure Instance details)](https://user-images.githubusercontent.com/28675258/67623220-c7ee3680-f7f0-11e9-9a30-08b03726f4f3.PNG)
![Lauch instance#4 (Configure Instance details - Add Storage](https://user-images.githubusercontent.com/28675258/67623221-c7ee3680-f7f0-11e9-94e4-60d87c3ce495.PNG)
![Lauch instance#5 (Configure Instance details - Add Tags)](https://user-images.githubusercontent.com/28675258/67623222-c7ee3680-f7f0-11e9-8907-4d8c959a7325.PNG)
![Lauch instance#6 (Configure Instance details - Configure Security Group)](https://user-images.githubusercontent.com/28675258/67623223-c7ee3680-f7f0-11e9-9d30-341e2a643766.PNG)
![Lauch instance#7 (Configure Instance details - Launch status failed!)](https://user-images.githubusercontent.com/28675258/67623224-c7ee3680-f7f0-11e9-8dda-1b1d9df8f0b7.PNG)
![Lauch instance#8 (Launch instance complete)](https://user-images.githubusercontent.com/28675258/67623225-c7ee3680-f7f0-11e9-999c-738481687b46.PNG)
![Lauch instance#9 (Launch instance using PuTTy#1)](https://user-images.githubusercontent.com/28675258/67623226-c7ee3680-f7f0-11e9-809d-56f04a9fca04.PNG)
![Lauch instance#10 (Launch instance using PuTTy#2)](https://user-images.githubusercontent.com/28675258/67623227-c886cd00-f7f0-11e9-980b-df8fb8f5be2e.PNG)
![Lauch instance#11 (Dowloaded updates)](https://user-images.githubusercontent.com/28675258/67623228-c886cd00-f7f0-11e9-9d3b-188d58f74db8.PNG)
![Download PuTTY from - putty org](https://user-images.githubusercontent.com/28675258/67623237-d9374300-f7f0-11e9-98f4-9453c8d068b0.PNG)
