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

# AWS Application Deployment, CI/CD and Systems Management

## 1. AWS Elastic Beanstalk

### 1. What is AWS Elastic Beanstalk?
AWS Elastic Beanstalk is a Platform as a Service (PaaS) that makes it easier to deploy, manage, and scale web applications without manually managing the underlying infrastructure.

### 2. Why do we use it?
- To deploy applications easily.
- To reduce infrastructure management work.
- To automatically manage resources such as EC2, load balancers, and Auto Scaling.
- To monitor application health.

### 3. How does it work?
1. Upload application code.
2. Select the programming platform.
3. Elastic Beanstalk creates the required AWS environment.
4. It provisions resources such as EC2 instances.
5. The application becomes accessible through an environment URL.
6. It provides monitoring and application health information.

### 4. Real-world use cases
- Hosting web applications.
- Deploying Python, Java, Node.js, and .NET applications.
- Running application environments for development and production.

### 5. Hands-on implementation
1. Open AWS Management Console.
2. Search for Elastic Beanstalk.
3. Select Create application.
4. Enter an application name.
5. Select the platform.
6. Upload sample application code.
7. Create the environment.
8. Wait until the environment becomes healthy.
9. Open the environment URL to test the application.

**Important concepts:**
- Application: Logical collection of environments and versions.
- Environment: The AWS resources running the application.
- Application version: A specific version of uploaded application code.
- Environment health: Indicates the operational health of the environment.

---

## 2. Elastic Beanstalk Hands-on

### 1. What did I practise?
I practised deploying a web application using AWS Elastic Beanstalk.

### 2. Why did I practise it?
To understand how AWS can automatically provision infrastructure and deploy an application.

### 3. How does it work?
- Created a Beanstalk application.
- Selected an application platform.
- Uploaded sample application code.
- Created an environment.
- Waited for deployment to complete.
- Accessed the application using its environment URL.

### 4. Real-world use cases
- Testing application deployments.
- Hosting web applications.
- Quickly creating application environments.

### 5. Hands-on learning outcome
I learned how to deploy and access an application using Elastic Beanstalk without manually creating every infrastructure resource.

---

## 3. AWS CodeDeploy

### 1. What is AWS CodeDeploy?
AWS CodeDeploy is an AWS deployment service that automates application deployments to computing services such as Amazon EC2, on-premises servers, AWS Lambda, and Amazon ECS.

### 2. Why do we use it?
- To automate application deployments.
- To reduce manual deployment errors.
- To manage application updates.
- To support controlled deployment strategies.

### 3. How does it work?
1. Prepare application files.
2. Create an application in CodeDeploy.
3. Configure a deployment group.
4. Provide an AppSpec file describing deployment instructions.
5. Start a deployment.
6. CodeDeploy deploys the application to the selected targets.

### 4. Real-world use cases
- Deploying new application versions.
- Updating applications on EC2 instances.
- Deploying Lambda function versions.
- Automating application releases.

### 5. Hands-on concepts
Learn these important components:
- Application: Identifies the application to deploy.
- Deployment group: Defines the deployment targets.
- Revision: The application version being deployed.
- AppSpec file: Specifies deployment instructions.
- Deployment configuration: Controls how deployment occurs.

---

## 4. AWS CodeCommit

### 1. What is AWS CodeCommit?
AWS CodeCommit is a managed source control service that hosts private Git repositories. Developers can store, manage, and collaborate on source code using Git.

### 2. Why do we use it?
- To store source code securely.
- To maintain code versions.
- To collaborate with development teams.
- To manage code changes using Git.

### 3. How does it work?
1. Create a repository in CodeCommit.
2. Clone the repository to a local computer.
3. Add or modify files.
4. Commit changes using Git.
5. Push changes to the remote repository.
6. Other authorized developers can pull changes.

### 4. Real-world use cases
- Hosting application source code.
- Managing team development projects.
- Maintaining code history.
- Integrating source code with CI/CD workflows.

### 5. Hands-on concepts
Practise:
- Creating a repository.
- Cloning a repository.
- Adding files.
- Committing changes.
- Pushing and pulling changes.

**Note:** CodeCommit is AWS's managed Git repository service. GitHub is a separate source-code hosting platform.

---

## 5. AWS CodeBuild

### 1. What is AWS CodeBuild?
AWS CodeBuild is a fully managed continuous integration (CI) service that compiles source code, runs tests, and produces software build artifacts.

### 2. Why do we use it?
- To automate application builds.
- To run automated tests.
- To reduce manual build work.
- To generate deployment-ready artifacts.

### 3. How does it work?
1. Connect a source code repository.
2. Create a CodeBuild project.
3. Configure the build environment.
4. Define build instructions in a buildspec.yml file.
5. Start the build.
6. CodeBuild runs the commands and produces build artifacts.

### 4. Real-world use cases
- Building Java applications.
- Testing Python applications.
- Compiling application code.
- Preparing application packages for deployment.

### 5. Important concepts
- Build project: Configuration for a build.
- Build environment: Environment used to run build commands.
- Buildspec.yml: File containing build instructions.
- Build artifact: Output generated after a successful build.

**Example buildspec.yml:**

```yaml
version: 0.2

phases:
  build:
    commands:
      - echo "Building application"
      - echo "Build completed successfully"
```

---

## 6. AWS CodePipeline

### 1. What is AWS CodePipeline?
AWS CodePipeline is a continuous delivery (CD) service that automates the stages involved in releasing software.

### 2. Why do we use it?
- To automate software release workflows.
- To connect source, build, test, and deployment stages.
- To reduce manual release activities.
- To deliver application updates consistently.

### 3. How does it work?
A typical pipeline contains these stages:

1. Source: Gets application code from a repository.
2. Build: Uses CodeBuild to build and test the code.
3. Test: Performs additional testing if configured.
4. Deploy: Deploys the application using a deployment service such as CodeDeploy.

### 4. Real-world use cases
- Automating application releases.
- Deploying updates whenever developers push code.
- Creating continuous delivery workflows.
- Managing development and production release stages.

### 5. Important concepts
- Pipeline: Complete automated workflow.
- Stage: A major step in the workflow.
- Action: An individual operation within a stage.
- Source provider: Location from which code is retrieved.
- Approval action: Can require manual approval before proceeding.

---

## 7. AWS CodeArtifact

### 1. What is AWS CodeArtifact?
AWS CodeArtifact is a fully managed artifact repository service used to securely store, publish, and share software packages and dependencies.

### 2. Why do we use it?
- To store software packages.
- To manage application dependencies.
- To share packages across development teams.
- To control access to internal packages.

### 3. How does it work?
1. Create a CodeArtifact domain.
2. Create a repository.
3. Configure a supported package manager.
4. Authenticate with CodeArtifact.
5. Publish or download software packages.

### 4. Real-world use cases
- Storing Python packages.
- Managing Java dependencies.
- Sharing internal software libraries.
- Managing dependencies in CI/CD pipelines.

### 5. Important concepts
- Domain: Groups repositories.
- Repository: Stores software packages.
- Package: A reusable software component.
- Package version: A specific version of a package.
- Upstream repository: Allows a repository to retrieve packages from another repository.

---

## 8. AWS Systems Manager (SSM)

### 1. What is AWS Systems Manager?
AWS Systems Manager is an AWS service that helps manage, monitor, automate, and operate AWS resources and hybrid environments.

### 2. Why do we use it?
- To manage EC2 instances centrally.
- To execute commands remotely.
- To automate operational tasks.
- To manage configuration and parameters.
- To improve operational visibility.

### 3. How does it work?
1. Configure the required IAM permissions.
2. Ensure the managed instance has the SSM Agent and required connectivity.
3. Register or connect the instance with Systems Manager.
4. Use Systems Manager features to manage the instance.
5. Monitor operations and command execution results.

### 4. Real-world use cases
- Running commands on EC2 instances remotely.
- Automating software installation.
- Managing configuration settings.
- Securely accessing instances using Session Manager.
- Storing application configuration values.

### 5. Important concepts
- SSM Agent: Software that enables Systems Manager to communicate with supported managed instances.
- Session Manager: Provides interactive access without requiring SSH or RDP access.
- Run Command: Executes commands remotely.
- Automation: Automates operational tasks.
- Parameter Store: Stores configuration data and secrets.

---

## 9. Systems Manager Hands-on

### 1. What did I practise?
I practised using AWS Systems Manager to manage an EC2 instance.

### 2. Why did I practise it?
To understand how EC2 instances can be managed remotely without connecting through a traditional SSH session.

### 3. How does it work?
1. Launch an EC2 instance with a suitable IAM instance profile.
2. Ensure the SSM Agent is installed and running.
3. Ensure the instance has network connectivity to Systems Manager endpoints.
4. Open AWS Systems Manager.
5. Select Session Manager or Run Command.
6. Connect to the instance or execute a command.
7. View the command execution result.

### 4. Real-world use cases
- Remote server administration.
- Executing commands across multiple instances.
- Troubleshooting EC2 instances.
- Automating routine operations.

### 5. Hands-on learning outcome
I learned how to use Systems Manager to access and manage EC2 instances remotely.

---

## 10. AWS Systems Manager Parameter Store

### 1. What is Parameter Store?
Parameter Store is a capability of AWS Systems Manager that securely stores configuration data and secrets as parameters.

### 2. Why do we use it?
- To store application configuration.
- To centralize configuration management.
- To avoid hardcoding configuration values in application code.
- To store sensitive values using encrypted parameters.

### 3. How does it work?
1. Open AWS Systems Manager.
2. Select Parameter Store.
3. Create a parameter.
4. Enter a parameter name and value.
5. Choose a parameter type.
6. Save the parameter.
7. Retrieve the parameter from an application or AWS service using appropriate permissions.

### 4. Real-world use cases
- Storing database connection settings.
- Storing application environment configurations.
- Managing API keys and tokens.
- Sharing configuration values between applications.

### 5. Important parameter types
- String: Stores ordinary text values.
- StringList: Stores comma-separated string values.
- SecureString: Stores sensitive values using encryption through AWS KMS.

**Example parameter:**

```text
Name: /myapp/database/host
Type: String
Value: mydatabase.example.com
```

**Important:** SecureString is suitable for sensitive values, but AWS Secrets Manager may be more appropriate when you need features such as built-in secret rotation and lifecycle management.

---

## 11. Quick Comparison of AWS Services

| Service | Main purpose |
|---|---|
| Elastic Beanstalk | Deploy and manage web applications |
| CodeDeploy | Automate application deployments |
| CodeCommit | Host Git repositories |
| CodeBuild | Build and test source code |
| CodePipeline | Automate CI/CD workflows |
| CodeArtifact | Store and manage software packages |
| Systems Manager | Manage and automate AWS resources |
| Parameter Store | Store configuration values and secrets |

## 12. What I Learned Today

- Learned how AWS Elastic Beanstalk deploys applications.
- Practised deploying a sample application using Beanstalk.
- Understood automated application deployment with CodeDeploy.
- Learned source-code management using CodeCommit.
- Understood application building and testing using CodeBuild.
- Learned CI/CD workflow automation using CodePipeline.
- Understood package and dependency management using CodeArtifact.
- Learned AWS Systems Manager and its management capabilities.
- Practised managing an EC2 instance using SSM.
- Learned how to create and retrieve parameters using Parameter Store.