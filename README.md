# IAC-with-AWS-Cloud-Formation

## Overview
In this hands-on exercise, I explored **AWS CloudFormation** to create AWS resources using **Infrastructure as Code (IaC)**. The goal was to understand how to automate resource provisioning instead of creating them manually.

For this, I created:

- **S3 Bucket** with encryption and secure access  
- **DynamoDB Table** with streams enabled  
- **IAM User Group** for managing permissions  

![Alt Text](image-path-or-URL)

## What I Did

### 1. S3 Bucket
- Created a bucket with a unique name using stack name and account ID.  
- Enabled **server-side encryption** with AWS KMS.  
- Blocked public access to secure the bucket.  
- Added a bucket policy to enforce **HTTPS-only access**.  

### 2. DynamoDB Table
- Created a table named `Table` with `id` as the primary key.  
- Set billing to **pay-per-request** for cost efficiency.  
- Enabled **streams** to capture both new and old images of items.  

### 3. IAM Group
- Created a basic **IAM group**.  
- This group can be used to attach policies for user management.
  # Hands-On: AWS CloudFormation IaC


The **stack name** I used for this lab is: `s3-bucket-dynamodb-iam-usergroup`.

## How I Created the Stack

### Step 1: Log in to AWS Console
1. Go to the [AWS Management Console](https://aws.amazon.com/console/).  
2. Navigate to **CloudFormation / Infrastructure Composer** under **Services**.

### Step 2: Create a New Stack
1. Click **Create stack** → **With new resources (standard)**.  
2. Choose **Upload a template file**.  
3. Click **Choose file** and select your YAML template (`main.yaml`).  
4. Click **Next**.

### Step 3: Specify Stack Details
1. Enter the **stack name**: `s3-bucket-dynamodb-iam-usergroup`.  
2. (Optional) Add **tags** to organize resources.  
3. Click **Next**.

### Step 4: Configure Stack Options
1. (Optional) Configure advanced options like **IAM roles, stack policies, and rollback settings**.  
2. Click **Next**.

![Alt Text](image-path-or-URL)

### Step 5: Review and Create
1. Review all stack details carefully.  
2. Acknowledge that CloudFormation might create IAM resources by checking the box **“I acknowledge that AWS CloudFormation might create IAM resources”**.  
3. Click **Create stack**.

![Alt Text](image-path-or-URL)

### Step 6: Monitor Stack Creation
- Wait for the status to show **CREATE_COMPLETE**.  

### Step 7: Verify Resources
- Go to **S3** to check the bucket with encryption and HTTPS-only policy.  
- Go to **DynamoDB** to see the table and streams enabled.  
- Go to **IAM** to check the newly created user group.

![Alt Text](image-path-or-URL)
![Alt Text](image-path-or-URL)
![Alt Text](image-path-or-URL)

### Step 8: Clean Up (Optional)
To delete all resources created by the stack:  
1. Go to the **CloudFormation console**.  
2. Select your stack and click **Delete**.  
3. Confirm deletion to remove all resources.

## What I Learned
- How to define AWS resources using **CloudFormation / Infrastructure Composer**.  
- How to enforce **S3 security best practices**.  
- How to create **DynamoDB tables with streams**.  
- How to manage **IAM groups** through IaC.


