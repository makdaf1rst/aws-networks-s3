<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Access S3 from a VPC

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-s3)

**Author:** saqibh49@gmail.com  
**Email:** saqibh49@gmail.com

---

## Access S3 from a VPC

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-s3_3e1e79a2)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is your own private section of the AWS cloud where you can set up networks, subnets, and security rules however you want, and it is useful because it keeps your data secure and isolated from the public internet while still letting you connect the resources that need to talk to each other.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create an ec2 instance, connect to it, create an s3, then connect to my s3 bucket via the ec2 instance. 

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how simple it would be to connect to my s3 from my ec2 instance. 

### This project took me...

This project took me 30 minutes. 

---

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will set up my VPC and an instance within it because that is how I will be able to then access an S3 bucket from within my instance. 

### Step 2 - Connect to my EC2 instance

In this step, I will connect to my instance because by connecting to it, I can try to access my S3 bucket. 

### Step 3 - Set up access keys

In this step, I will create access keys for my EC2 instance because this will give it access to my AWS resources. 

---

## Architecture set up

I started my project by launching a VPC along with a public subnet, then I launched an instance inside of my VPC.

I also set up an S3 bucket and added 2 image files to it for starters. 

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-s3_4334d777)

---

## Running CLI commands

AWS CLI is a way of accessing and managing AWS resources directly from the command line. I have access to AWS CLI because the AWS management console has a terminal built in, so I can access CLI even without downloading it to my local computer. 

The first command I ran was aws s2 ls. This command is used to list out all S3 buckets in my AWS account. 

The second command I ran was aws configure. This command is used to set up my access keys. 

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-s3_e7fa8776)

---

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured my instance by giving it my access keys so it can see the rest of my aws resources, even if they're outside the VPC. 

Access keys are credentials for servers and apps within AWS to use to log into AWS and communication with my AWS resources.

Secret access keys are like the password that pairs with my username. I need both to access AWS services. 

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use an IAM role with the correct permissions. 

---

## In the second part of my project...

### Step 4 - Set up an S3 bucket

In this step, I will launch a bucket in S3 so I can test out how to connect to it from my instance.

### Step 5 - Connecting to my S3 bucket

In this step, I will attempt to connect to my S3 bucket from my instance because this will help me get a better idea of things I might need to do in the future in a production environment. 

---

## Connecting to my S3 bucket

The first command I ran was aws s2 ls. This command is used to list out all S3 buckets in my AWS account. 

When I ran the command aws s3 ls again, the terminal responded with a list of s3 buckets in my account, in this case, ust the one bucket I created a minite ago. This indicated that my ec2 instance can now connect to the rest of my aws resources via my access key. 

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-s3_4334d778)

---

## Connecting to my S3 bucket

Another CLI command I ran was aws s2 ls s3/nextwork-vpc-project-saqib which returned the contents of my s3 bucket, the two images I uploaded previously. 

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-s3_4334d779)

---

## Uploading objects to S3

To create a new file, I first ran the command sudo touch /tmp/test.txt. This command creates a new blank text file. 

The second command I ran was aws s3 cp /tmp/test.txt s3://nextwork-vpc-project-saqib. This command will move the blank text file I just created into my s3 bucket. 

The third command I ran was aws s3 ls s3://nextwork-vpc-project-saqib, which validated that the file was moved into my s3 bucket by listing out the bucket's contents.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-s3_3e1e79a2)

---

---
