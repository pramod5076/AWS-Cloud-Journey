\# AWS Global Applications and Route 53



\## 1. Global Applications



\### 1. What are Global Applications?

Global applications are applications designed to serve users across different geographical locations around the world with high availability, low latency, and better performance.



\### 2. Why do we use Global Applications?

\- To serve users worldwide.

\- To reduce network latency.

\- To improve application availability.

\- To support disaster recovery.

\- To provide a better user experience.



\### 3. How do Global Applications work?

1\. Users access an application from different countries.

2\. DNS services direct users to appropriate application endpoints.

3\. AWS services route requests to suitable resources.

4\. Content is delivered through nearby edge locations.

5\. Multiple AWS Regions can help maintain application availability.



\### 4. Real-world use cases

\- Global e-commerce websites.

\- International banking applications.

\- Video streaming platforms.

\- Online gaming applications.

\- Worldwide business applications.



\### 5. Important Concepts

\- \*\*AWS Regions:\*\* Geographical areas where AWS operates its infrastructure.

\- \*\*Availability Zones:\*\* Isolated locations within an AWS Region.

\- \*\*Edge Locations:\*\* Locations used to deliver content closer to users.

\- \*\*Amazon CloudFront:\*\* A Content Delivery Network (CDN) that delivers content globally.

\- \*\*Amazon Route 53:\*\* A DNS service that routes users to application endpoints.

\- \*\*AWS Global Accelerator:\*\* Improves global application availability and performance using the AWS global network.



\---



\## 2. Amazon Route 53



\### 1. What is Amazon Route 53?

Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service provided by AWS. It translates domain names into IP addresses and helps route users to application endpoints.



\*\*Example:\*\* When a user enters `www.example.com` in a browser, Route 53 helps resolve the domain name to the appropriate destination.



\### 2. Why do we use Route 53?

\- To register domain names.

\- To manage DNS records.

\- To route users to AWS resources.

\- To improve application availability.

\- To perform DNS health checks and failover.

\- To manage global traffic routing.



\### 3. How does Route 53 work?

1\. A user enters a domain name in a browser.

2\. The DNS resolver sends a DNS query.

3\. Route 53 responds with the appropriate DNS record.

4\. The browser connects to the returned destination.

5\. The application responds to the user.



\### 4. Real-world use cases

\- Connecting a domain name to a website.

\- Routing users to different AWS Regions.

\- Distributing traffic across multiple servers.

\- Implementing DNS failover.

\- Managing domain names and subdomains.



\### 5. Important Concepts



\*\*Hosted Zone:\*\* A container that holds DNS records for a domain.



\*\*DNS Records:\*\* Entries that define how domain names are resolved.



\*\*Health Checks:\*\* Monitor the health of endpoints and support DNS failover configurations.



\*\*TTL (Time to Live):\*\* The time a DNS response can remain cached by DNS resolvers.



\*\*Route 53 Routing Policies:\*\*



1\. \*\*Simple Routing:\*\* Routes traffic to a resource using a simple DNS record.

2\. \*\*Weighted Routing:\*\* Distributes traffic across multiple resources based on assigned weights.

3\. \*\*Latency-Based Routing:\*\* Routes users to the Region that provides the lowest network latency.

4\. \*\*Failover Routing:\*\* Routes traffic to a primary resource and switches to a secondary resource when the primary is unhealthy.

5\. \*\*Geolocation Routing:\*\* Routes users based on their geographical location.

6\. \*\*Geoproximity Routing:\*\* Routes traffic based on the geographic location of users and resources.

7\. \*\*Multivalue Answer Routing:\*\* Returns multiple healthy resource values in response to DNS queries.



# AWS Global Infrastructure and Global Applications

## 1. Amazon CloudFront

### 1. What is Amazon CloudFront?
Amazon CloudFront is a Content Delivery Network (CDN) service provided by AWS. It delivers website content, images, videos, and other files to users through a global network of edge locations.

### 2. Why do we use CloudFront?
- To reduce content delivery latency.
- To deliver content faster to users worldwide.
- To reduce the load on origin servers.
- To improve website performance.
- To provide secure content delivery.

### 3. How does it work?
1. A user requests content from a website.
2. The request reaches a nearby CloudFront edge location.
3. CloudFront checks whether the requested content is cached.
4. If cached, CloudFront delivers the content from the edge location.
5. If not cached, CloudFront retrieves it from the origin server and can cache it for future requests.

### 4. Real-world use cases
- Delivering website images and videos.
- Streaming video content.
- Improving global website performance.
- Delivering static and dynamic web content.

### 5. Important Concepts
- **Distribution:** Configuration that tells CloudFront how to deliver content.
- **Origin:** The original location where content is stored, such as an S3 bucket or web server.
- **Edge Location:** A location where CloudFront caches and delivers content.
- **Cache:** Temporarily stores content to serve future requests faster.
- **TTL:** Determines how long content remains cached.
- **Invalidation:** Removes selected cached objects from CloudFront edge locations.
- **Origin Access Control (OAC):** Helps securely allow CloudFront to access private S3 bucket content.

---

## 2. CloudFront Hands-on

### 1. What did I practise?
I practised configuring Amazon CloudFront to deliver content through its global network.

### 2. Why did I practise it?
To understand how CloudFront distributes content and improves website loading performance.

### 3. How does it work?
- Configured a CloudFront distribution.
- Selected an origin for content delivery.
- Created the distribution.
- Accessed the content using the CloudFront distribution domain name.
- Observed how CloudFront delivers content.

### 4. Real-world use cases
- Delivering static website content.
- Improving website loading speed.
- Delivering content to users in different geographical locations.

### 5. What I learned
I understood how CloudFront distributions, origins, edge locations, and caching work together to deliver content globally.

---

## 3. Amazon S3 Transfer Acceleration

### 1. What is S3 Transfer Acceleration?
Amazon S3 Transfer Acceleration is an S3 feature that speeds up uploading files to an S3 bucket over long geographical distances by using AWS edge locations and the AWS global network.

### 2. Why do we use it?
- To improve upload speeds over long distances.
- To transfer large files faster.
- To improve data transfer performance for globally distributed users.

### 3. How does it work?
1. A user uploads a file using the S3 Transfer Acceleration endpoint.
2. The request reaches a nearby AWS edge location.
3. The data travels through the AWS global network.
4. The data reaches the destination S3 bucket.

### 4. Real-world use cases
- Uploading large files from different countries.
- Global applications that upload data to S3.
- Transferring media files and backups over long distances.

### 5. Important Concepts
- **Edge Location:** The nearby AWS location that receives the upload.
- **Accelerated Endpoint:** Special S3 endpoint used for accelerated transfers.
- **AWS Global Network:** AWS network infrastructure used to transport data.

---

## 4. AWS Global Accelerator

### 1. What is AWS Global Accelerator?
AWS Global Accelerator is a networking service that improves the availability and performance of applications for global users by directing traffic through the AWS global network.

### 2. Why do we use it?
- To improve global application performance.
- To reduce network latency.
- To improve application availability.
- To provide static anycast IP addresses.
- To route traffic to healthy application endpoints.

### 3. How does it work?
1. Global Accelerator provides static anycast IP addresses.
2. Users connect to the nearest AWS edge location.
3. Traffic enters the AWS global network.
4. Global Accelerator routes traffic to a healthy application endpoint.
5. Traffic reaches the selected AWS Region or endpoint.

### 4. Real-world use cases
- Global online gaming applications.
- International business applications.
- Applications hosted across multiple AWS Regions.
- Applications requiring high availability.

### 5. Important Concepts
- **Static Anycast IP:** Fixed IP addresses that direct users to nearby AWS edge locations.
- **Listener:** Accepts incoming traffic on specified ports and protocols.
- **Endpoint Group:** Groups endpoints in a specific AWS Region.
- **Endpoint:** The destination resource, such as an Application Load Balancer, Network Load Balancer, EC2 instance, or Elastic IP address.
- **Health Check:** Helps identify healthy and unhealthy endpoints.

---

## 5. AWS Outposts

### 1. What is AWS Outposts?
AWS Outposts is a fully managed service that extends AWS infrastructure, services, APIs, and tools to a customer's on-premises location.

### 2. Why do we use it?
- To run AWS services on-premises.
- To support applications requiring low latency.
- To process data locally.
- To meet certain data residency and local processing requirements.
- To maintain a consistent AWS experience across cloud and on-premises environments.

### 3. How does it work?
1. AWS installs Outposts infrastructure at the customer's location.
2. The Outposts equipment connects to an AWS Region.
3. Customers use supported AWS services locally.
4. Applications can process data on-premises while integrating with the AWS Region.

### 4. Real-world use cases
- Manufacturing industries.
- Healthcare organizations.
- Financial institutions.
- Applications requiring local data processing.
- Environments with strict data residency requirements.

### 5. Important Concepts
- **Outposts Rack:** AWS infrastructure installed at a customer's facility.
- **Outposts Server:** Smaller Outposts form factor for suitable locations.
- **Local Processing:** Running supported workloads close to where data is generated.

---

## 6. AWS Wavelength

### 1. What is AWS Wavelength?
AWS Wavelength brings AWS compute and storage services to the edge of telecommunications providers' 5G networks.

### 2. Why do we use it?
- To support ultra-low-latency applications.
- To process data closer to mobile users.
- To reduce the distance data travels.
- To support real-time mobile applications.

### 3. How does it work?
1. AWS infrastructure is deployed within a telecommunications provider's network.
2. Applications run on supported AWS Wavelength infrastructure.
3. Mobile users access the applications through the 5G network.
4. Data is processed closer to the users.

### 4. Real-world use cases
- 5G gaming applications.
- Connected vehicles.
- Smart factories.
- Real-time video processing.
- Augmented and virtual reality applications.

### 5. Important Concepts
- **Wavelength Zone:** An AWS infrastructure deployment within a telecommunications provider's 5G network.
- **5G Network:** Provides high-speed mobile connectivity.
- **Low Latency:** Reduces the time required for data to travel between users and applications.

---

## 7. AWS Local Zones

### 1. What are AWS Local Zones?
AWS Local Zones are infrastructure deployments that place selected AWS compute, storage, and other services closer to large population centers and users.

### 2. Why do we use them?
- To run applications closer to end users.
- To reduce latency.
- To support applications requiring local processing.
- To deliver better performance for latency-sensitive workloads.

### 3. How do they work?
1. AWS deploys infrastructure in a location closer to users.
2. Customers extend their AWS applications and workloads to a Local Zone.
3. Applications process requests closer to users.
4. They can connect with the parent AWS Region for other services and operations.

### 4. Real-world use cases
- Media and entertainment applications.
- Real-time gaming.
- Virtual desktop infrastructure.
- Low-latency applications.
- Applications requiring local data processing.

### 5. Important Concepts
- **Local Zone:** AWS infrastructure located near a major city or population center.
- **Parent Region:** The AWS Region associated with a Local Zone.
- **Low Latency:** Faster communication between users and applications because resources are geographically closer.

---

## 8. Global Application Architecture

### 1. What is Global Application Architecture?
Global Application Architecture is the design of an application that serves users across different geographical locations using AWS global infrastructure and networking services.

### 2. Why do we use it?
- To serve users worldwide.
- To improve application performance.
- To reduce latency.
- To increase application availability.
- To support disaster recovery.

### 3. How does it work?
1. Users access an application from different countries.
2. Route 53 provides DNS resolution and routing.
3. CloudFront delivers cached content through edge locations.
4. AWS Global Accelerator can route application traffic through the AWS global network.
5. Application resources run in one or more AWS Regions.
6. Multiple Availability Zones help improve regional availability.

### 4. Real-world use cases
- Global e-commerce websites.
- International banking platforms.
- Video streaming applications.
- Online gaming platforms.
- Worldwide enterprise applications.

### 5. Important Concepts
- **Amazon Route 53:** DNS resolution and traffic routing.
- **Amazon CloudFront:** Global content delivery and caching.
- **AWS Global Accelerator:** Improves global application traffic performance and availability.
- **AWS Regions:** Geographical areas containing AWS infrastructure.
- **Availability Zones:** Isolated locations within AWS Regions.
- **Edge Locations:** Locations used by AWS services to bring content and network access closer to users.

