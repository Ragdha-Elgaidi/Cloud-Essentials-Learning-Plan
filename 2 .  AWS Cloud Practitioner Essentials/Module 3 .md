#  AWS global infrastructure
-  AWS operates in all sorts of different areas around the world called Regions.
## Selecting a Region
#### When determining the right Region for your services, data, and applications, consider the following four business factors.
- compliance with data governance and legal requirements
  - Depending on your company and location, you might need to run your data out of specific areas. For example, if your company requires                all of its data to reside within the boundaries of the UK, you would choose the London Region.
  
  - Not all companies have location-specific data regulations, so you might need to focus more on the other three factors.
- proximity to your customers
   - Selecting a Region that is close to your customers will help you to get content to them faster. For example, your company is based in Washington, DC, and many of your customers live in Singapore. You might consider running your infrastructure in the Northern Virginia Region to be close to company headquarters and run your applications from the Singapore Region.
- available services within a region
  - Sometimes, the closest Region might not have all the features that you want to offer to customers. AWS is frequently innovating by creating new services and expanding on features within existing services. However, making new services available around the world sometimes requires AWS to build out physical hardware one Region at a time. 
  - Suppose that your developers want to build an application that uses Amazon Braket (AWS quantum computing platform). As of this course, Amazon Braket is not yet available in every AWS Region around the world, so your developers would have to run it in one of the Regions that already offers it.
- pricing
   - Suppose that you are considering running applications in both the United States and Brazil. The way Brazil’s tax structure is set up, it might cost 50% more to run the same workload out of the São Paulo Region compared to the Oregon Region. You will learn in more detail that several factors determine pricing, but for now know that the cost of services can vary from Region to Region.
## Availability Zones
![c2inxaM8fnZZe7Ou_zBL1ijNGsMMu3-4j](https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/2508ec20-d8f6-48b9-a773-dd50ad7f692c)
-  An Availability Zone is a single data center or a group of data centers within a Region. Availability Zones are located tens of miles apart from each other. This is close enough to have low latency (the time between when content requested and received) between Availability Zones. However, if a disaster occurs in one part of the Region, they are distant enough to reduce the chance that multiple Availability Zones are affected.
### Running Amazon EC2 instances in multiple Availability Zones  
##### Amazon EC2 instance in a single Availability Zone
- Suppose that you’re running an application on a single Amazon EC2 instance in the Northern California Region. The instance is running in the us-west-1a Availability Zone. If us-west-1a were to fail, you would lose your instance.
- 
![AxsmfJsA0-Dw_fIK_n5sucbTNdewt_xQ9](https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/1e52b3d1-6540-400c-ae51-91bc013ad7a4)
##### Amazon EC2 instances in multiple Availability Zones
- A best practice is to run applications across at least two Availability Zones in a Region. In this example, you might choose to run a second Amazon EC2 instance in us-west-1b.
- 
![MV2GBC9NnP_1ScNR_qQcW9jf2SuLzltON](https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/1b7c4cef-f4f7-4bec-bfb4-118e0c9e5312)
##### Availability Zone failure
- If us-west-1a were to fail, your application would still be running in us-west-1b.
  
  ![qk0fWUNJ1n3Wt0nF_JPefG4t-k_6Fub-M](https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/0a3f23b5-1ae4-4c14-b988-d31684ec69a2)

- Planning for failure and deploying applications across multiple Availability Zones is an important part of building a resilient and highly available architecture.
# Edge locations
- site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery.
- Caching copies of data closer to the customers all around the world uses the concept of content delivery networks, or CDNs. 
CDNs are commonly used, and on AWS, we call our CDN Amazon CloudFront. Amazon CloudFront is a service that helps deliver data, video, applications, and APIs to customers around the world with low latency and high transfer speeds. Amazon CloudFront uses what are called Edge locations, all around the world, to help accelerate communication with users, no matter where they are. 
- Edge locations are separate from Regions, so you can push content from inside a Region to a collection of Edge locations around the world, in order to accelerate communication and content delivery. AWS Edge locations, also run more than just CloudFront. They run a domain name service, or DNS, known as Amazon Route 53, helping direct customers to the correct web locations with reliably low latency.
- what if your business wants to use, AWS services inside their own building? Well sure. AWS can do that for you. Introducing AWS Outposts, where AWS will basically install a fully operational mini Region, right inside your own data center. That's owned and operated by AWS, using 100% of AWS functionality, but isolated within your own building. It's not a solution most customers need, but if you have specific problems that can only be solved by staying in your own building, we understand, AWS Outposts can help. 


## Note:
- AWS global infrastructure, but let's keep it simple and stop here. So here's the key points. Number one, Regions are geographically isolated areas, where you can access services needed to run your enterprise. Number two, Regions contain Availability Zones, that allow you to run across physically separated buildings, tens of miles of separation, while keeping your application logically unified. Availability Zones help you solve high availability and disaster recovery scenarios, without any additional effort on your part, and number three, AWS Edge locations run Amazon CloudFront to help get content closer to your customers, no matter where they are in the world.
# How to provision AWS resources
- You may be wondering, how do I actually interact with these services? And the answer is APIs. In AWS, everything is an API call. An API is an application programming interface. And what that means is, there are pre determined ways for you to interact with AWS services. And you can invoke or call these APIs to provision, configure, and manage your AWS resources. 
## Ways to interact with AWS services
### AWS Management Console
- a web-based interface for accessing and managing AWS services. You can quickly access recently used services and search for other services by name, keyword, or acronym. The console includes wizards and automated workflows that can simplify the process of completing tasks.
- You can also use the AWS Console mobile application to perform tasks such as monitoring resources, viewing alarms, and accessing billing information. Multiple identities can stay logged into the AWS Console mobile app at the same time
### AWS Command Line Interface (AWS CLI)
- To save time when making API requests, you can use the AWS Command Line Interface (AWS CLI). AWS CLI enables you to control multiple AWS services directly from the command line within one tool. AWS CLI is available for users on Windows, macOS, and Linux. 
- By using AWS CLI, you can automate the actions that your services and applications perform through scripts. For example, you can use commands to launch an Amazon EC2 instance, connect an Amazon EC2 instance to a specific Auto Scaling group, and more.
### software development kits (SDKs)
- SDKs make it easier for you to use AWS services through an API designed for your programming language or platform. SDKs enable you to use AWS services with your existing applications or create entirely new applications that will run on AWS.
- To help you get started with using SDKs, AWS provides documentation and sample code for each supported programming language. Supported programming languages include C++, Java, .NET, and more.
## AWS Elastic Beanstalk
- With AWS Elastic Beanstalk, you provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:
    - Adjust capacity
    - Load balancing
    - Automatic scaling
    - Application health monitoring
- Instead of clicking around the console or writing multiple commands to build out your network, EC2 instances, scaling and Elastic Load Balancers, you can instead provide your application code and desired configurations to the AWS Elastic Beanstalk service, which then takes that information and builds out your environment for you. AWS Elastic Beanstalk also makes it easy to save environment configurations, so they can be deployed again easily. AWS Elastic Beanstalk gives you the convenience of not having to provision and manage all of these pieces separately, while still giving you the visibility and control of the underlying resources. You get to focus on your business application, not the infrastructure. 
## AWS CloudFormation
- With AWS CloudFormation, you can treat your infrastructure as code. This means that you can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.
- service you can use to help create automated and repeatable deployments
- infrastructure as code tool that allows you to define a wide variety of AWS resources in a declarative way using JSON or YAML text-based documents called CloudFormation templates. A declarative format like this allows you to define what you want to build without specifying the details of exactly how to build it. CloudFormation lets you define what you want and the CloudFormation engine will worry about the details on calling APIs to get everything built out.
- It also isn't just limited to EC2-based solutions. CloudFormation supports many different AWS resources from storage, databases, analytics, machine learning, and more. Once you define your resources in a CloudFormation template, CloudFormation will parse the template and begin provisioning all the resources you defined in parallel. CloudFormation manages all the calls to the backend AWS APIs for you. You can run the same CloudFormation template in multiple accounts or multiple regions, and it will create identical environments across them. There is less room for human error as it is a totally automated process.
- 
- AWS CloudFormation provisions your resources in a safe, repeatable manner, enabling you to frequently build your infrastructure and applications without having to perform manual actions. It determines the right operations to perform when managing your stack and rolls back changes automatically if it detects errors.
