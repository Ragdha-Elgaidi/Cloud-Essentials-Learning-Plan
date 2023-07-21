# AWS Free Tier
- The AWS Free Tier enables you to begin using certain services without having to worry about incurring costs for the specified period. 
- Three types of offers are available: 
   - Always Free
   - 12 Months Free
   - Trials
## For each free tier offer, make sure to review the specific details about exactly which resource types are included.
- Always Free
   - These offers do not expire and are available to all AWS customers.
   - For example, AWS Lambda allows 1 million free requests and up to 3.2 million seconds of compute time per month. Amazon DynamoDB allows 25 GB of free storage per month
- 12 Months Free
  - These offers are free for 12 months following your initial sign-up date to AWS.
  - Examples include specific amounts of Amazon S3 Standard Storage, thresholds for monthly hours of Amazon EC2 compute time, and amounts of Amazon CloudFront data transfer out
- Trials 
  - Short-term free trial offers start from the date you activate a particular service. The length of each trial might vary by number of days or the amount of usage in the service.
 - For example, Amazon Inspector offers a 90-day free trial. Amazon Lightsail (a service that enables you to run virtual private servers) offers 750 free hours of usage over a 30-day period.
# AWS pricing concepts
## How AWS pricing works
- pay for what you use
  - For each service, you pay for exactly the amount of resources that you actually use, without requiring long-term contracts or complex licensing
- pay less when you reserve
  - Some services offer reservation options that provide a significant discount compared to On-Demand Instance pricing.
  - For example, suppose that your company is using Amazon EC2 instances for a workload that needs to run continuously. You might choose to run this workload on Amazon EC2 Instance Savings Plans, because the plan allows you to save up to 72% over the equivalent On-Demand Instance capacity.
- pay less with volume based  discounts when you use more
  - Some services offer tiered pricing, so the per-unit cost is incrementally lower with increased usage.
  - For example, the more Amazon S3 storage space you use, the less you pay for it per GB.
## AWS pricing examples
- AWS Lambda
  - For AWS Lambda, you are charged based on the number of requests for your functions and the time that it takes for them to run.
  - AWS Lambda allows 1 million free requests and up to 3.2 million seconds of compute time per month.
  - You can save on AWS Lambda costs by signing up for a Compute Savings Plan. A Compute Savings Plan offers lower compute costs in exchange for committing to a consistent amount of usage over a 1-year or 3-year term. This is an example of paying less when you reserve.
- Amazon EC2
  - With Amazon EC2, you pay for only the compute time that you use while your instances are running.
  - For some workloads, you can significantly reduce Amazon EC2 costs by using Spot Instances. For example, suppose that you are running a batch processing job that is able to withstand interruptions. Using a Spot Instance would provide you with up to 90% cost savings while still meeting the availability requirements of your workload.
 - You can find additional cost savings for Amazon EC2 by considering Savings Plans and Reserved Instances.
- Amazon S3
  - For Amazon S3 pricing, consider the following cost components:
     - Storage - You pay for only the storage that you use. You are charged the rate to store objects in your Amazon S3 buckets based on your objects’ sizes, storage classes, and how long you have stored each object during the month.
    Requests and data retrievals - You pay for requests made to your Amazon S3 objects and buckets. For example, suppose that you are storing photo files in Amazon S3 buckets and hosting them on a website. Every time a visitor requests the website that includes these photo files, this counts towards requests you must pay for.
    -  Data transfer - There is no cost to transfer data between different Amazon S3 buckets or from Amazon S3 to other services within the same AWS Region. However, you pay for data that you transfer into and out of Amazon S3, with a few exceptions. There is no cost for data transferred into Amazon S3 from the internet or out to Amazon CloudFront. There is also no cost for data transferred out to an Amazon EC2 instance in the same AWS Region as the Amazon S3 bucket.
    - Management and replication - You pay for the storage management features that you have enabled on your account’s Amazon S3 buckets. These features include Amazon S3 inventory, analytics, and object tagging.
# Billing dashboard
- Use the AWS Billing & Cost Management dashboard to pay your AWS bill, monitor your usage, and analyze and control your costs.
   - Compare your current month-to-date balance with the previous month, and get a forecast of the next month based on current usage.
   - View month-to-date spend by service.
   - View Free Tier usage by service.
   - Access Cost Explorer and create budgets.
   - Purchase and manage Savings Plans.
   - Publish AWS Cost and Usage Reports.
# Consolidated billing
- The consolidated billing feature of AWS Organizations enables you to receive a single bill for all AWS accounts in your organization. By consolidating, you can easily track the combined costs of all the linked accounts in your organization. The default maximum number of accounts allowed for an organization is 4, but you can contact AWS Support to increase your quota, if needed.
- On your monthly bill, you can review itemized charges incurred by each account. This enables you to have greater transparency into your organization’s accounts while still maintaining the convenience of receiving a single monthly bill.
- Another benefit of consolidated billing is the ability to share bulk discount pricing, Savings Plans, and Reserved Instances across the accounts in your organization. For instance, one account might not have enough monthly usage to qualify for discount pricing. However, when multiple accounts are combined, their aggregated usage may result in a benefit that applies across all accounts in the organization.
# AWS Budgets
- In AWS Budgets, you can create budgets to plan your service usage, service costs, and instance reservations.
- The information in AWS Budgets updates three times a day. This helps you to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.
- In AWS Budgets, you can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.
## Example: AWS Budgets
- Suppose that you have set a budget for Amazon EC2. You want to ensure that your company’s usage of Amazon EC2 does not exceed $200 for the month. 
- In AWS Budgets, you could set a custom budget to notify you when your usage has reached half of this amount ($100). This setting would allow you to receive an alert and decide how you would like to proceed with your continued use of Amazon EC2.
# AWS Cost Explorer
-  a tool that enables you to visualize, understand, and manage your AWS costs and usage over time.
- AWS Cost Explorer includes a default report of the costs and usage for your top five cost-accruing AWS services. You can apply custom filters and groups to analyze your data. For example, you can view resource usage at the hourly level.
# AWS Support plans
- offers four different Support plans to help you troubleshoot issues, lower costs, and efficiently use AWS services. 
- You can choose from the following Support plans to meet your company’s needs: 
   - Basic
   - Developer
   - Business
   - Enterprise On-Ramp
   - Enterprise
## Basic Support
- Basic Support is free for all AWS customers. It includes access to whitepapers, documentation, and support communities. With Basic Support, you can also contact AWS for billing questions and service limit increases.
- With Basic Support, you have access to a limited selection of AWS Trusted Advisor checks. Additionally, you can use the AWS Personal Health Dashboard, a tool that provides alerts and remediation guidance when AWS is experiencing events that may affect you. 
- If your company needs support beyond the Basic level, you could consider purchasing Developer, Business, Enterprise On-Ramp, and Enterprise Support.
## Developer, Business, Enterprise On-Ramp, and Enterprise Support
- The Developer, Business, Enterprise On-Ramp, and Enterprise Support plans include all the benefits of Basic Support, in addition to the ability to open an unrestricted number of technical support cases. These Support plans have pay-by-the-month pricing and require no long-term contracts.
- The information in this course highlights only a selection of details for each Support plan. A complete overview of what is included in each Support plan, including pricing for each plan, is available on the AWS Support site.
- In general, for pricing, the Developer plan has the lowest cost, the Business and Enterprise On-Ramp plans are in the middle, and the Enterprise plan has the highest cost.
### Developer support
- Customers in the Developer Support plan have access to features such as:
   - Best practice guidance
   - Client-side diagnostic tools
   - Building-block architecture support, which consists of guidance for how to use AWS offerings, features, and services together
- For example, suppose that your company is exploring AWS services. You’ve heard about a few different AWS services. However, you’re unsure of how to potentially use them together to build applications that can address your company’s needs. In this scenario, the building-block architecture support that is included with the Developer Support plan could help you to identify opportunities for combining specific services and features.
### Business support
- Customers with a Business Support plan have access to additional features, including: 
    Use-case guidance to identify AWS offerings, features, and services that can best support your specific needs
    All AWS Trusted Advisor checks
    Limited support for third-party software, such as common operating systems and application stack components
- Suppose that your company has the Business Support plan and wants to install a common third-party operating system onto your Amazon EC2 instances. You could contact AWS Support for assistance with installing, configuring, and troubleshooting the operating system. For advanced topics such as optimizing performance, using custom scripts, or resolving security issues, you may need to contact the third-party software provider directly.
### Enterprise on ramp support
- In November 2021, AWS opened enrollment into AWS Enterprise On-Ramp Support plan. In addition to all the features included in the Basic, Developer, and Business Support plans, customers with an Enterprise On-Ramp Support plan have access to:

    - A pool of Technical Account Managers to provide proactive guidance and coordinate access to programs and AWS experts

    - A Cost Optimization workshop (one per year)

    - A Concierge support team for billing and account assistance

    - Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard
- Enterprise On-Ramp Support plan also provides access to a specific set of proactive support services, which are provided by a pool of Technical Account Managers.

   - Consultative review and architecture guidance (one per year)

   - Infrastructure Event Management support (one per year)

   - Support automation workflows

   - 30 minutes or less response time for business-critical issues
### Enterprise suppport
- In addition to all features included in the Basic, Developer, Business, and Enterprise On-Ramp support plans, customers with Enterprise Support have access to:
   - A designated Technical Account Manager to provide proactive guidance and coordinate access to programs and AWS experts

   - A Concierge support team for billing and account assistance

   - Operations Reviews and tools to monitor health

   - Training and Game Days to drive innovation

   - Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard

- The Enterprise plan also provides full access to proactive services, which are provided by a designated Technical Account Manager:

   - Consultative review and architecture guidance

   - Infrastructure Event Management support

   - Cost Optimization Workshop and tools

   - Support automation workflows

   - 15 minutes or less response time for business-critical issues
## Technical Account Manager (TAM)
- The Enterprise On-Ramp and Enterprise Support plans include access to a Technical Account Manager (TAM).
- The TAM is your primary point of contact at AWS. If your company subscribes to Enterprise Support or Enterprise On-Ramp, your TAM educates, empowers, and evolves your cloud journey across the full range of AWS services. TAMs provide expert engineering guidance, help you design solutions that efficiently integrate AWS services, assist with cost-effective and resilient architectures, and provide direct access to AWS programs and a broad community of experts.
- For example, suppose that you are interested in developing an application that uses several AWS services together. Your TAM could provide insights into how to best use the services together. They achieve this, while aligning with the specific needs that your company is hoping to address through the new application.
# AWS Marketplace
-  a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS. 
- For each listing in AWS Marketplace, you can access detailed information on pricing options, available support, and reviews from other AWS customers.
- You can also explore software solutions by industry and use case. For example, suppose that your company is in the healthcare industry. In AWS Marketplace, you can review use cases that software helps you to address, such as implementing solutions to protect patient records or using machine learning models to analyze a patient’s medical history and predict possible health risks.
- AWS Marketplace offers products in several categories, such as Infrastructure Software, DevOps, Data Products, Professional Services, Business Applications, Machine Learning, Industries, and Internet of Things (IoT).

- Within each category, you can narrow your search by browsing through product listings in subcategories. For example, subcategories in the DevOps category include areas such as Application Development, Monitoring, and Testing.
