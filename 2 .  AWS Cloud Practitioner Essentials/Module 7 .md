# Amazon CloudWatch 
- a web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics.
- CloudWatch uses metrics to represent the data points for your resources. AWS services send metrics to CloudWatch. CloudWatch then uses these metrics to create graphs automatically that show how performance has changed over time.
## CloudWatch alarms
- With CloudWatch, you can create alarms that automatically perform actions if the value of your metric has gone above or below a predefined threshold. 
- For example, suppose that your company’s developers use Amazon EC2 instances for application development or testing purposes. If the developers occasionally forget to stop the instances, the instances will continue to run and incur charges. 
- In this scenario, you could create a CloudWatch alarm that automatically stops an Amazon EC2 instance when the CPU utilization percentage has remained below a certain threshold for a specified period. When configuring the alarm, you can specify to receive a notification whenever this alarm is triggered.
## CloudWatch dashboard

<img width="840" alt="HeRaopuap7qzOpRr_rLfuExSsSpuXOVqf" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/2680a9cc-d6ba-4039-ac05-8314ac7daf38">

- The CloudWatch dashboard feature enables you to access all the metrics for your resources from a single location. For example, you can use a CloudWatch dashboard to monitor the CPU utilization of an Amazon EC2 instance, the total number of requests made to an Amazon S3 bucket, and more. You can even customize separate dashboards for different business purposes, applications, or resources.
# AWS CloudTrail
- records API calls for your account. The recorded information includes the identity of the API caller, the time of the API call, the source IP address of the API caller, and more. You can think of CloudTrail as a “trail” of breadcrumbs (or a log of actions) that someone has left behind them.
- Recall that you can use API calls to provision, manage, and configure your AWS resources. With CloudTrail, you can view a complete history of user activity and API calls for your applications and resources. 
- Events are typically updated in CloudTrail within 15 minutes after an API call. You can filter events by specifying the time and date that an API call occurred, the user who requested the action, the type of resource that was involved in the API call, and more.
- Example: AWS CloudTrail event
    - Suppose that the coffee shop owner is browsing through the AWS Identity and Access Management (IAM) section of the AWS Management Console. They discover that a new IAM user named Mary was created, but they do not who, when, or which method created the user.
    - To answer these questions, the owner navigates to AWS CloudTrail.
<img width="840" alt="DuFP-7CaCRak-bWB_LpdzY_ElDiXoJpKQ" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/958e3ec7-72a9-45e2-afbb-9aa8f12e3042">

- In the CloudTrail Event History section, the owner applies a filter to display only the events for the “CreateUser” API action in IAM. The owner locates the event for the API call that created an IAM user for Mary. This event record provides complete details about what occurred: 
- On January 1, 2020 at 9:00 AM, IAM user John created a new IAM user (Mary) through the AWS Management Console.
## CloudTrail Insights
- Within CloudTrail, you can also enable CloudTrail Insights. This optional feature allows CloudTrail to automatically detect unusual API activities in your AWS account. 
- For example, CloudTrail Insights might detect that a higher number of Amazon EC2 instances than usual have recently launched in your account. You can then review the full event details to determine which actions you need to take next.
# AWS Trusted Advisor
- a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices.
- Trusted Advisor compares its findings to AWS best practices in five categories: cost optimization, performance, security, fault tolerance, and service limits. For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. 
- The guidance provided by AWS Trusted Advisor can benefit your company at all stages of deployment. For example, you can use AWS Trusted Advisor to assist you while you are creating new workflows and developing new applications. Or you can use it while you are making ongoing improvements to existing applications and resources.
## AWS Trusted Advisor dashboard

![ZDxhrgkzFSK89kX__2gGWhu3Np9FWdzHm](https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/471102d8-a7c4-47a5-bba8-939f86ba4dae)

- When you access the Trusted Advisor dashboard on the AWS Management Console, you can review completed checks for cost optimization, performance, security, fault tolerance, and service limits.

- For each category:
     - The green check indicates the number of items for which it detected no problems.
     - The orange triangle represents the number of recommended investigations.
     - The red circle represents the number of recommended actions.
