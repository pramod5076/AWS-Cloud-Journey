\# AWS Compute Services



This document contains my learning notes about compute services and technologies, their working principles, real-world applications, and hands-on implementations.



\---



\# 1. Docker



\## 1. What is Docker?

Docker is a platform used to develop, package, and run applications inside containers. A container includes an application and its required dependencies, making it easier to run consistently across different environments.



Note: Docker is a containerization technology, not an AWS service.



\## 2. Why do we use Docker?

\- Application portability.

\- Consistent application environments.

\- Lightweight compared to traditional virtual machines.

\- Faster application deployment.

\- Easy application scaling.

\- Simplifies application development and testing.



\## 3. How does it work?

1\. Developers write application code.

2\. A Dockerfile defines the application environment.

3\. Docker builds an image using the Dockerfile.

4\. A container is created from the image.

5\. The container runs the application with its dependencies.



\### Important Concepts

\- Dockerfile: Instructions used to build a Docker image.

\- Docker Image: A packaged template used to create containers.

\- Docker Container: A running instance of an image.

\- Docker Hub: A registry for storing and sharing container images.

\- Docker Engine: Software responsible for building and running containers.

\- Containerization: Packaging applications and dependencies into containers.



\## 4. Real-World Use Cases

\- Microservices applications.

\- Application development and testing.

\- Cloud application deployment.

\- CI/CD pipelines.

\- Consistent development environments.



\## 5. Hands-On Practical Implementation

1\. Install Docker Desktop.

2\. Open the terminal.

3\. Verify Docker installation using `docker --version`.

4\. Run a test container using `docker run hello-world`.

5\. Download an image using `docker pull nginx`.

6\. Run an Nginx container.

7\. Explore running containers using `docker ps`.

8\. Stop and remove a container.



\---



\# 2. Amazon ECS (Elastic Container Service)



\## 1. What is Amazon ECS?

Amazon ECS is a fully managed container orchestration service provided by AWS. It helps deploy, manage, and scale containerized applications.



\## 2. Why do we use it?

\- Manage Docker containers.

\- Deploy containerized applications.

\- Automatically scale applications.

\- Simplify container management.

\- Integrate with other AWS services.

\- Run microservices applications.



\## 3. How does it work?

1\. Create or obtain a Docker image.

2\. Store the image in a container registry such as Amazon ECR.

3\. Create an ECS task definition.

4\. Create an ECS cluster.

5\. Run tasks or create a service.

6\. ECS manages container deployment and scheduling.



\### Important Concepts

\- Cluster: A logical grouping of ECS resources.

\- Task Definition: A blueprint describing how containers should run.

\- Task: A running instance of a task definition.

\- Service: Maintains the desired number of running tasks.

\- Container Instance: An EC2 instance that can host ECS tasks when using EC2 capacity.

\- Amazon ECR: A container registry for storing Docker images.



\## 4. Real-World Use Cases

\- Microservices applications.

\- Web application deployment.

\- Backend API services.

\- Containerized enterprise applications.

\- Scalable application hosting.



\## 5. Hands-On Practical Implementation

1\. Open AWS Management Console.

2\. Search for Amazon ECS.

3\. Create an ECS cluster.

4\. Explore task definitions.

5\. Configure a container image.

6\. Configure CPU and memory.

7\. Create a service or run a standalone task.

8\. Explore container logs and task status.



\---



\# 3. AWS Fargate



\## 1. What is AWS Fargate?

AWS Fargate is a serverless compute engine for containers. It allows users to run containers without managing the underlying EC2 servers.



\## 2. Why do we use it?

\- No need to manage EC2 instances.

\- Simplifies container deployment.

\- Automatically manages infrastructure capacity.

\- Supports containerized applications.

\- Pay for the compute resources used according to applicable pricing.



\## 3. How does it work?

1\. Create a container image.

2\. Define the container configuration.

3\. Choose Fargate as the compute launch type or capacity provider for ECS or EKS.

4\. Specify CPU and memory requirements.

5\. Submit the container workload.

6\. AWS manages the underlying compute infrastructure.



\### Important Concepts

\- Serverless Containers: Run containers without managing servers.

\- CPU: Processing capacity allocated to the workload.

\- Memory: RAM allocated to the container.

\- Task: A running container workload in ECS.

\- ECS: Can use Fargate to run containers.

\- EKS: Can use Fargate to run supported Kubernetes pods.



\## 4. Real-World Use Cases

\- Microservices.

\- Web applications.

\- API services.

\- Background processing.

\- Containerized applications with varying workloads.



\## 5. Hands-On Practical Implementation

1\. Open Amazon ECS.

2\. Create an ECS cluster.

3\. Select a Fargate-based configuration.

4\. Create a task definition.

5\. Configure container image, CPU, and memory.

6\. Configure networking.

7\. Run a Fargate task.

8\. Monitor the task status.



\---



\# 4. Amazon EKS (Elastic Kubernetes Service)



\## 1. What is Amazon EKS?

Amazon EKS is a managed Kubernetes service provided by AWS. It helps users deploy, manage, and scale containerized applications using Kubernetes.



\## 2. Why do we use it?

\- Manage containerized applications.

\- Automate container orchestration.

\- Scale applications.

\- Manage complex microservices.

\- Use the Kubernetes ecosystem.

\- Reduce the effort of managing the Kubernetes control plane.



\## 3. How does it work?

1\. Create an EKS cluster.

2\. Kubernetes manages the application workloads.

3\. Deploy applications using Kubernetes manifests.

4\. Kubernetes schedules pods onto available compute capacity.

5\. Kubernetes manages scaling, service discovery, and workload recovery.



\### Important Concepts

\- Kubernetes: An open-source container orchestration platform.

\- Cluster: A collection of Kubernetes control-plane and worker resources.

\- Node: A machine that runs application workloads.

\- Pod: The smallest deployable unit in Kubernetes.

\- Deployment: Defines and manages application replicas.

\- Service: Provides a stable way to access application pods.

\- kubectl: Command-line tool used to interact with Kubernetes.



\## 4. Real-World Use Cases

\- Large-scale microservices.

\- Enterprise applications.

\- Cloud-native applications.

\- Multi-container applications.

\- Applications requiring Kubernetes orchestration.



\## 5. Hands-On Practical Implementation

1\. Open Amazon EKS.

2\. Explore cluster creation.

3\. Understand Kubernetes node groups.

4\. Explore Fargate profiles.

5\. Learn about pods and deployments.

6\. Understand how `kubectl` communicates with EKS.

7\. Explore application deployment and monitoring.



\---



\# 5. AWS Lambda



\## 1. What is AWS Lambda?

AWS Lambda is a serverless compute service that allows users to run code without provisioning or managing servers.



\## 2. Why do we use it?

\- No server management.

\- Automatic scaling.

\- Event-driven execution.

\- Pay based on requests and execution duration.

\- Easy integration with other AWS services.



\## 3. How does it work?

1\. Write a function.

2\. Upload the code to AWS Lambda.

3\. Configure the function.

4\. Set up an event source or invoke the function directly.

5\. Lambda executes the code when triggered.

6\. The function returns a result or performs an action.



\### Important Concepts

\- Function: The code executed by Lambda.

\- Trigger: An event that invokes a Lambda function.

\- Runtime: The programming language environment.

\- Event: Data passed to a Lambda function.

\- Execution Role: IAM role that defines the permissions available to the function.

\- Timeout: Maximum time allowed for a function invocation.



\## 4. Real-World Use Cases

\- Image processing.

\- File processing.

\- Backend API development.

\- Automated notifications.

\- Scheduled tasks.

\- Event-driven applications.



\## 5. Hands-On Practical Implementation

1\. Open AWS Management Console.

2\. Search for AWS Lambda.

3\. Select Create Function.

4\. Choose Author from Scratch.

5\. Enter a function name.

6\. Select a supported runtime, such as Python.

7\. Create the function.

8\. Write a simple function.

9\. Deploy the code.

10\. Create a test event.

11\. Execute the function.

12\. Explore execution results and CloudWatch logs.



\---



\# 6. AWS Lambda Hands-On: Create and Test a Function



\## Objective

Create a simple AWS Lambda function and execute it using a test event.



\## Implementation



\### Step 1: Create a Lambda Function

1\. Open AWS Lambda.

2\. Click Create Function.

3\. Select Author from Scratch.

4\. Enter the function name: `MyFirstLambda`.

5\. Select Python as the runtime.

6\. Create the function.



\### Step 2: Add Python Code



```python

def lambda\_handler(event, context):

&#x20;   name = event.get("name", "AWS Learner")



&#x20;   return {

&#x20;       "statusCode": 200,

&#x20;       "body": f"Hello, {name}! Welcome to AWS Lambda."

&#x20;   }

```



\### Step 3: Deploy

1\. Click Deploy.

2\. Wait for the deployment to complete.



\### Step 4: Create a Test Event



Use this JSON test event:



```json

{

&#x20;   "name": "Pramod"

}

```



\### Step 5: Execute

1\. Click Test.

2\. Execute the Lambda function.

3\. Check the execution result.



\### Expected Output



```text

Hello, Pramod! Welcome to AWS Lambda.

```



\### What I Learned

\- How to create a Lambda function.

\- How to write Python code in Lambda.

\- How to deploy a function.

\- How to create a test event.

\- How to execute and monitor a function.



\---



\# 7. Amazon API Gateway



\## 1. What is Amazon API Gateway?

Amazon API Gateway is a fully managed AWS service used to create, publish, secure, monitor, and manage APIs.



It allows applications to communicate with backend services such as AWS Lambda.



\## 2. Why do we use it?

\- Create REST APIs and HTTP APIs.

\- Connect applications to backend services.

\- Manage API requests.

\- Apply authentication and authorization.

\- Monitor API performance.

\- Build serverless applications.



\## 3. How does it work?

1\. A client sends an HTTP request.

2\. API Gateway receives the request.

3\. API Gateway routes it to the configured backend.

4\. The backend processes the request.

5\. The response is returned to the client through API Gateway.



\### Important Concepts

\- API: An interface for communication between applications.

\- Endpoint: A URL through which an API can be accessed.

\- HTTP Methods: GET, POST, PUT, DELETE.

\- Integration: Connects an API route to a backend.

\- Authentication: Verifies the identity of a user or application.

\- Authorization: Determines what an authenticated identity is allowed to do.



\## 4. Real-World Use Cases

\- Mobile application backends.

\- Serverless web applications.

\- E-commerce APIs.

\- Payment application integrations.

\- Backend services for web applications.



\## 5. Hands-On Practical Implementation

1\. Open Amazon API Gateway.

2\. Create an HTTP API.

3\. Add a route such as GET /hello.

4\. Configure AWS Lambda as the integration.

5\. Deploy the API.

6\. Copy the API endpoint.

7\. Open the endpoint in a browser or use an API client.

8\. Verify the response from Lambda.



\---



\# 8. AWS Batch



\## 1. What is AWS Batch?

AWS Batch is a managed service that helps run large numbers of batch computing jobs on AWS.



\## 2. Why do we use it?

\- Run large-scale batch workloads.

\- Automate job scheduling.

\- Manage compute resources.

\- Process data in batches.

\- Optimize resource allocation.



\## 3. How does it work?

1\. Create a job definition.

2\. Configure a compute environment.

3\. Create a job queue.

4\. Submit a batch job.

5\. AWS Batch schedules the job.

6\. The job runs on available compute resources.

7\. Monitor the job status and results.



\### Important Concepts

\- Job: A unit of work submitted for execution.

\- Job Definition: Describes how a job should run.

\- Job Queue: Holds submitted jobs waiting for execution.

\- Compute Environment: Defines the compute resources available for jobs.

\- Scheduler: Selects jobs for execution based on configured rules.



\## 4. Real-World Use Cases

\- Financial data processing.

\- Scientific simulations.

\- Large-scale file processing.

\- Data transformation.

\- Media processing.

\- Research workloads.



\## 5. Hands-On Practical Implementation

1\. Open AWS Batch.

2\. Explore compute environments.

3\. Create or examine a job queue.

4\. Understand job definitions.

5\. Submit a sample batch job.

6\. Monitor job status.

7\. Explore job logs and results.



\---



\# 9. Amazon Lightsail



\## 1. What is Amazon Lightsail?

Amazon Lightsail is a simplified cloud platform provided by AWS. It offers easy-to-use virtual private servers, storage, networking, and other resources with predictable pricing options.



\## 2. Why do we use it?

\- Easy cloud server deployment.

\- Simple pricing plans.

\- Beginner-friendly interface.

\- Quick application hosting.

\- Reduced infrastructure configuration complexity.



\## 3. How does it work?

1\. Select an operating system or application blueprint.

2\. Choose a virtual server plan.

3\. Configure the instance.

4\. Launch the instance.

5\. Connect to the server using SSH.

6\. Deploy and manage applications.



\### Important Concepts

\- Instance: A virtual private server.

\- Blueprint: A preconfigured operating system or application.

\- Bundle: A plan containing compute, memory, storage, and data transfer allowances.

\- Static IP: A fixed public IP address.

\- Snapshot: A backup of a Lightsail resource.

\- Networking: Controls networking and firewall settings.



\## 4. Real-World Use Cases

\- Hosting websites.

\- WordPress websites.

\- Small business applications.

\- Development environments.

\- Personal projects.

\- Simple web servers.



\## 5. Hands-On Practical Implementation

1\. Open AWS Management Console.

2\. Search for Amazon Lightsail.

3\. Create an instance.

4\. Select a Linux or Windows blueprint.

5\. Choose an instance plan.

6\. Create the instance.

7\. Wait for it to become available.

8\. Connect using the browser-based SSH terminal or an appropriate remote access method.

9\. Explore instance networking.

10\. Understand snapshots and static IP addresses.



\---



\# 10. Amazon Lightsail Hands-On: Launch a Virtual Server



\## Objective

Launch a virtual server using Amazon Lightsail and understand how to access and manage it.



\### Step 1: Open Lightsail

1\. Open AWS Management Console.

2\. Search for Amazon Lightsail.

3\. Open the service.



\### Step 2: Create an Instance

1\. Select Create Instance.

2\. Choose the AWS Region and Availability Zone.

3\. Select Linux/Unix as the platform.

4\. Select an operating system blueprint such as Ubuntu.

5\. Choose an appropriate instance plan.



\### Step 3: Launch the Instance

1\. Enter an instance name.

2\. Review the configuration.

3\. Create the instance.

4\. Wait until the instance status becomes Running.



\### Step 4: Connect to the Instance

1\. Open the created instance.

2\. Select Connect using SSH.

3\. Open the browser-based terminal.

4\. Run basic Linux commands.



```bash

whoami

pwd

ls

uname -a

```



\### Step 5: Explore Networking

\- View the public IP address.

\- Explore firewall settings.

\- Understand SSH access.

\- Explore static IP configuration.



\### Step 6: Explore Snapshots

1\. Open the Snapshots section.

2\. Understand how instance backups work.

3\. Explore how a snapshot can be used to create another instance.



\### What I Learned

\- How to create a Lightsail instance.

\- How to select an operating system.

\- How to connect to a virtual server.

\- How to execute Linux commands.

\- How to explore networking and snapshots.



\---



\# Summary of AWS Compute Services



| Service / Technology | Main Purpose |

|---|---|

| Docker | Containerization |

| Amazon ECS | Container orchestration |

| AWS Fargate | Serverless container compute |

| Amazon EKS | Managed Kubernetes |

| AWS Lambda | Serverless code execution |

| API Gateway | API creation and management |

| AWS Batch | Batch job processing |

| Amazon Lightsail | Simplified cloud hosting |



\## Key Learning



AWS provides multiple compute services for different application requirements.



\- Docker packages applications into containers.

\- ECS manages containers using AWS orchestration.

\- Fargate runs containers without managing servers.

\- EKS manages Kubernetes clusters.

\- Lambda executes code in response to events.

\- API Gateway exposes APIs to applications.

\- AWS Batch manages batch computing jobs.

\- Lightsail simplifies virtual server deployment.



\## My Learning Outcome



I learned the fundamentals of AWS compute services, containerization, serverless computing, API management, batch processing, and virtual server hosting.



I also practiced creating a Lambda function and launching a Lightsail instance.

