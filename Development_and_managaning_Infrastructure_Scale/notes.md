\# AWS Development and Management – Infrastructure as Code



\## 1. AWS CloudFormation



\### 1. What is AWS CloudFormation?

AWS CloudFormation is an Infrastructure as Code (IaC) service that allows us to create, manage, and update AWS resources using templates written in YAML or JSON.



\### 2. Why do we use it?

\- To automate AWS resource creation.

\- To avoid manually creating resources one by one.

\- To manage infrastructure consistently.

\- To recreate the same infrastructure whenever required.



\### 3. How does it work?

1\. Write a CloudFormation template using YAML or JSON.

2\. Upload the template to AWS CloudFormation.

3\. Create a stack.

4\. CloudFormation reads the template.

5\. AWS resources are created automatically.

6\. We can update or delete the stack to manage its resources.



\*\*Important concepts:\*\*

\- Template: A YAML or JSON file describing AWS resources.

\- Stack: A collection of AWS resources managed together.

\- Resources: AWS services such as S3, EC2, and DynamoDB.

\- Parameters: Values supplied when creating or updating a stack.

\- Outputs: Information returned after stack creation.



\### 4. Real-world use cases

\- Automatically creating EC2 instances.

\- Creating S3 buckets.

\- Deploying networking resources such as VPCs and subnets.

\- Creating repeatable development and production environments.



\### 5. Hands-on implementation

1\. Open the AWS Management Console.

2\. Search for CloudFormation.

3\. Select \*\*Create stack\*\*.

4\. Choose \*\*Upload a template file\*\*.

5\. Upload your YAML template.

6\. Enter a stack name.

7\. Select the required options and create the stack.

8\. Check the stack status and its Resources tab.



\*\*Example YAML template – Create an S3 bucket\*\*



```yaml

AWSTemplateFormatVersion: '2010-09-09'

Description: Create an S3 bucket using CloudFormation



Resources:

&#x20; MyS3Bucket:

&#x20;   Type: AWS::S3::Bucket



Outputs:

&#x20; BucketName:

&#x20;   Description: Name of the created S3 bucket

&#x20;   Value: !Ref MyS3Bucket

```



\*\*Note:\*\* Select `us-east-1` in the AWS Console before creating the stack if you want the bucket created in that region. CloudFormation creates the bucket in the stack's selected region.



\---



\## 2. CloudFormation Hands-on



\### 1. What did I practise?

I used AWS CloudFormation to create an S3 bucket automatically through a YAML template.



\### 2. Why did I practise it?

To understand how Infrastructure as Code works and how AWS resources can be created without manually configuring every resource.



\### 3. How does it work?

\- Created a YAML template.

\- Uploaded the template to CloudFormation.

\- Created a stack.

\- CloudFormation created the S3 bucket.

\- Verified the bucket in the S3 console.



\### 4. Real-world use cases

\- Automating infrastructure deployment.

\- Creating identical environments.

\- Managing multiple AWS resources together.



\### 5. Hands-on learning outcome

I learned how to:

\- Write a basic CloudFormation YAML template.

\- Upload a template.

\- Create a CloudFormation stack.

\- Verify the resources created by the stack.



\*\*Important:\*\* Delete the test stack when finished if you no longer need it. Check the resources and any retained data before deletion.



\---



\## 3. AWS CDK (Cloud Development Kit)



\### 1. What is AWS CDK?

AWS Cloud Development Kit (CDK) is an open-source software development framework that allows developers to define AWS cloud infrastructure using programming languages such as Python, TypeScript, JavaScript, Java, and C#.



\### 2. Why do we use it?

\- To define infrastructure using programming languages.

\- To reduce manual configuration.

\- To reuse infrastructure code.

\- To automate AWS deployments.

\- To manage complex infrastructure more easily.



\### 3. How does it work?

1\. Write infrastructure code using a supported programming language.

2\. Use CDK constructs to define AWS resources.

3\. Run the CDK synthesis command.

4\. CDK generates a CloudFormation template.

5\. Deploy the template using CDK.

6\. CloudFormation creates or updates the AWS resources.



\### 4. Real-world use cases

\- Creating AWS infrastructure using Python or TypeScript.

\- Automating application environments.

\- Deploying S3 buckets, Lambda functions, and other AWS resources.

\- Reusing infrastructure definitions across projects.



\### 5. Basic CDK workflow



```bash

cdk init app --language python

cdk synth

cdk bootstrap

cdk deploy

```



\*\*Command explanations:\*\*

\- `cdk init`: Creates a new CDK project.

\- `cdk synth`: Generates a CloudFormation template.

\- `cdk bootstrap`: Prepares the AWS environment for CDK deployments.

\- `cdk deploy`: Deploys the infrastructure to AWS.



\*\*Note:\*\* AWS CDK requires the appropriate development tools and AWS credentials to be configured.



\---



\## 4. CloudFormation vs AWS CDK



| Feature | CloudFormation | AWS CDK |

|---|---|---|

| Purpose | Infrastructure as Code | Infrastructure as Code |

| Language | YAML or JSON | Programming languages |

| Output | Manages AWS resources | Generates CloudFormation templates |

| Coding style | Declarative templates | Programming code |

| Deployment | CloudFormation stacks | CDK deploys through CloudFormation |



\## 5. What I Learned Today



\- Understood Infrastructure as Code (IaC).

\- Learned how AWS CloudFormation works.

\- Created an S3 bucket using a YAML template.

\- Practised creating and managing a CloudFormation stack.

\- Learned the purpose of AWS CDK.

\- Understood the relationship between CDK and CloudFormation.



-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# AWS Development and Management – Infrastructure as Code

## 1. AWS CloudFormation

### 1. What is AWS CloudFormation?
AWS CloudFormation is an Infrastructure as Code (IaC) service that allows us to create, manage, and update AWS resources using templates written in YAML or JSON.

### 2. Why do we use it?
- To automate AWS resource creation.
- To avoid manually creating resources one by one.
- To manage infrastructure consistently.
- To recreate the same infrastructure whenever required.

### 3. How does it work?
1. Write a CloudFormation template using YAML or JSON.
2. Upload the template to AWS CloudFormation.
3. Create a stack.
4. CloudFormation reads the template.
5. AWS resources are created automatically.
6. We can update or delete the stack to manage its resources.

**Important concepts:**
- Template: A YAML or JSON file describing AWS resources.
- Stack: A collection of AWS resources managed together.
- Resources: AWS services such as S3, EC2, and DynamoDB.
- Parameters: Values supplied when creating or updating a stack.
- Outputs: Information returned after stack creation.

### 4. Real-world use cases
- Automatically creating EC2 instances.
- Creating S3 buckets.
- Deploying networking resources such as VPCs and subnets.
- Creating repeatable development and production environments.

### 5. Hands-on implementation
1. Open the AWS Management Console.
2. Search for CloudFormation.
3. Select **Create stack**.
4. Choose **Upload a template file**.
5. Upload your YAML template.
6. Enter a stack name.
7. Select the required options and create the stack.
8. Check the stack status and its Resources tab.

**Example YAML template – Create an S3 bucket**

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Create an S3 bucket using CloudFormation

Resources:
  MyS3Bucket:
    Type: AWS::S3::Bucket

Outputs:
  BucketName:
    Description: Name of the created S3 bucket
    Value: !Ref MyS3Bucket
```

**Note:** Select `us-east-1` in the AWS Console before creating the stack if you want the bucket created in that region. CloudFormation creates the bucket in the stack's selected region.

---

## 2. CloudFormation Hands-on

### 1. What did I practise?
I used AWS CloudFormation to create an S3 bucket automatically through a YAML template.

### 2. Why did I practise it?
To understand how Infrastructure as Code works and how AWS resources can be created without manually configuring every resource.

### 3. How does it work?
- Created a YAML template.
- Uploaded the template to CloudFormation.
- Created a stack.
- CloudFormation created the S3 bucket.
- Verified the bucket in the S3 console.

### 4. Real-world use cases
- Automating infrastructure deployment.
- Creating identical environments.
- Managing multiple AWS resources together.

### 5. Hands-on learning outcome
I learned how to:
- Write a basic CloudFormation YAML template.
- Upload a template.
- Create a CloudFormation stack.
- Verify the resources created by the stack.

**Important:** Delete the test stack when finished if you no longer need it. Check the resources and any retained data before deletion.

---

## 3. AWS CDK (Cloud Development Kit)

### 1. What is AWS CDK?
AWS Cloud Development Kit (CDK) is an open-source software development framework that allows developers to define AWS cloud infrastructure using programming languages such as Python, TypeScript, JavaScript, Java, and C#.

### 2. Why do we use it?
- To define infrastructure using programming languages.
- To reduce manual configuration.
- To reuse infrastructure code.
- To automate AWS deployments.
- To manage complex infrastructure more easily.

### 3. How does it work?
1. Write infrastructure code using a supported programming language.
2. Use CDK constructs to define AWS resources.
3. Run the CDK synthesis command.
4. CDK generates a CloudFormation template.
5. Deploy the template using CDK.
6. CloudFormation creates or updates the AWS resources.

### 4. Real-world use cases
- Creating AWS infrastructure using Python or TypeScript.
- Automating application environments.
- Deploying S3 buckets, Lambda functions, and other AWS resources.
- Reusing infrastructure definitions across projects.

### 5. Basic CDK workflow

```bash
cdk init app --language python
cdk synth
cdk bootstrap
cdk deploy
```

**Command explanations:**
- `cdk init`: Creates a new CDK project.
- `cdk synth`: Generates a CloudFormation template.
- `cdk bootstrap`: Prepares the AWS environment for CDK deployments.
- `cdk deploy`: Deploys the infrastructure to AWS.

**Note:** AWS CDK requires the appropriate development tools and AWS credentials to be configured.

---

## 4. CloudFormation vs AWS CDK

| Feature | CloudFormation | AWS CDK |
|---|---|---|
| Purpose | Infrastructure as Code | Infrastructure as Code |
| Language | YAML or JSON | Programming languages |
| Output | Manages AWS resources | Generates CloudFormation templates |
| Coding style | Declarative templates | Programming code |
| Deployment | CloudFormation stacks | CDK deploys through CloudFormation |

## 5. What I Learned Today

- Understood Infrastructure as Code (IaC).
- Learned how AWS CloudFormation works.
- Created an S3 bucket using a YAML template.
- Practised creating and managing a CloudFormation stack.
- Learned the purpose of AWS CDK.
- Understood the relationship between CDK and CloudFormation.

