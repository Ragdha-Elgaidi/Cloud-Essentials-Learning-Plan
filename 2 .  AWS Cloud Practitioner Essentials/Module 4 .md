# Connectivity to AWS
## Amazon Virtual Private Cloud, or VPCs
- A VPC lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. These resources can be public facing so they have access to the internet, or private with no internet access, usually for backend services like databases or application servers. The public and private grouping of resources are known as subnets and they are ranges of IP addresses in your VPC.
- A networking service that you can use to establish boundaries around your AWS resources
## Internet gateway(IGW)
- To allow public traffic from the internet to access your VPC, you attach an internet gateway to the VPC.
-  connection between a VPC and the internet

    <img width="840" alt="vthQ7SNTsuyClU9w_NEblbQjD0vn0-pPU" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/94118b53-9095-424a-8b21-57b205206252">
### What if you have a VPC that includes only private resources?
To access private resources in a VPC, you can use a virtual private gateway
## Virtual private gateway
- Here’s an example of how a virtual private gateway works. You can think of the internet as the road between your home and the coffee shop. Suppose that you are traveling on this road with a bodyguard to protect you. You are still using the same road as other customers, but with an extra layer of protection. 

- The bodyguard is like a virtual private network (VPN) connection that encrypts (or protects) your internet traffic from all the other requests around it. 

- The virtual private gateway is the component that allows protected internet traffic to enter into the VPC.
<img width="840" alt="l6TOPFdq56BwNLzb_s8U3lQzEONXm1FMX" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/d214caf0-14db-462a-bdff-2f6c4f54cb56">

- A virtual private gateway enables you to establish a virtual private network (VPN) connection between your VPC and a private network, such as an on-premises data center or internal corporate network. A virtual private gateway allows traffic into the VPC only if it is coming from an approved network.
- We don't want just anyone from anywhere to be able to reach these resources. So we don't want an internet gateway attached to our VPC. Instead, we want a private gateway that only allows people in if they are coming from an approved network, not the public internet. This private doorway is called a virtual private gateway, and it allows you to create a VPN connection between a private network, like your on-premises data center or internal corporate network to your VPC. 



## AWS Direct Connect
- a service that enables you to establish a dedicated private connection between your data center and a VPC.
- Suppose that there is an apartment building with a hallway directly linking the building to the coffee shop. Only the residents of the apartment building can travel through this hallway. 

- This private hallway provides the same type of dedicated connection as AWS Direct Connect. Residents are able to get into the coffee shop without needing to use the public road shared with other customers.
- The private connection that AWS Direct Connect provides helps you to reduce network costs and increase the amount of bandwidth that can travel through your network.
  <img width="840" alt="J-OFNyD3j-0JCfWl_YdzRvczPABE_j-yV" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/0f70a683-8961-4726-8407-688433f0ede9">
# Subnets and network access control lists
- a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private
- Public subnets contain resources that need to be accessible by the public, such as an online store’s website.
- Private subnets contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories. 
- In a VPC, subnets can communicate with each other. For example, you might have an application that involves Amazon EC2 instances in a public subnet communicating with databases that are located in a private subnet.
<img width="597" alt="3yv1DP1G-Bp_TKwW_pi4TpfvEYaalWuIu" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/c44e6c46-98a8-4175-a466-3e2dc03ab1ca">

## Network traffic in a VPC
- When a customer requests data from an application hosted in the AWS Cloud, this request is sent as a packet. A packet is a unit of data sent over the internet or a network. 
- It enters into a VPC through an internet gateway. Before a packet can enter into a subnet or exit from a subnet, it checks for permissions. These permissions indicate who sent the packet and how the packet is trying to communicate with the resources in a subnet.
- The VPC component that checks packet permissions for subnets is a network access control list (ACL).
## Network access control lists (ACLs)
- a virtual firewall that controls inbound and outbound traffic at the subnet level.
- For example, In the airport, travelers are trying to enter into a different country. You can think of the travelers as packets and the passport control officer as a network ACL. The passport control officer checks travelers’ credentials when they are both entering and exiting out of the country. If a traveler is on an approved list, they are able to get through. However, if they are not on the approved list or are explicitly on a list of banned travelers, they cannot come in.
- Each AWS account includes a default network ACL. When configuring your VPC, you can use your account’s default network ACL or create custom network ACLs.
- By default, your account’s default network ACL allows all inbound and outbound traffic, but you can modify it by adding your own rules. For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic to allow. Additionally, all network ACLs have an explicit deny rule. This rule ensures that if a packet doesn’t match any of the other rules on the list, the packet is denied.

<img width="563" alt="3VvC_sZaItiPLSyu_e5z0Nx1wJ-H36Lsd" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/5f8c3e51-db86-4fb5-8b12-372378cfc80e">

## Stateless packet filtering
- Network ACLs perform stateless packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound. 
- Recall the previous example of a traveler who wants to enter into a different country. This is similar to sending a request out from an Amazon EC2 instance and to the internet.
- When a packet response for that request comes back to the subnet, the network ACL does not remember your previous request. The network ACL checks the packet response against its list of rules to determine whether to allow or deny.
- After a packet has entered a subnet, it must have its permissions evaluated for resources within the subnet, such as Amazon EC2 instances. 
- The VPC component that checks packet permissions for an Amazon EC2 instance is a security group.
## Security groups
- a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance.
- By default, a security group denies all inbound traffic and allows all outbound traffic. You can add custom rules to configure which traffic to allow or deny.

- For this example, suppose that you are in an apartment building with a door attendant who greets guests in the lobby. You can think of the guests as packets and the door attendant as a security group. As guests arrive, the door attendant checks a list to ensure they can enter the building. However, the door attendant does not check the list again when guests are exiting the building

- If you have multiple Amazon EC2 instances within a subnet, you can associate them with the same security group or use different security groups for each instance. 
## Stateful packet filtering
- Security groups perform stateful packet fil<img width="840" alt="90uyZt9Op_XmDsxa_ha8um-1InZb0jryB" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/57226e35-8f89-465e-8a56-6cf9b9a316ff">
tering. They remember previous decisions made for incoming packets.
- Consider the same example of sending a request out from an Amazon EC2 instance to the internet. 
- When a packet response for that request returns to the instance, the security group remembers your previous request. The security group allows the response to proceed, regardless of inbound security group rules.
- Both network ACLs and security groups enable you to configure custom rules for the traffic in your VPC.
# Global networking
## Domain Name System (DNS)
- Suppose that AnyCompany has a website hosted in the AWS Cloud. Customers enter the web address into their browser, and they are able to access the website. This happens because of Domain Name System (DNS) resolution. DNS resolution involves a customer DNS resolver communicating with a company DNS server.
- You can think of DNS as being the phone book of the internet. DNS resolution is the process of translating a domain name to an IP address

<img width="840" alt="LOQvC2LzaLPOU5Xn_AFBIDcTkYnYj1OOb" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/2d279ccf-c36a-4289-ae32-f78ee7075ce9">

## Amazon Route 53
-  a DNS web service. It gives developers and businesses a reliable way to route end users to internet applications hosted in AWS.
-  Amazon Route 53 connects user requests to infrastructure running in AWS (such as Amazon EC2 instances and load balancers). It can route users to infrastructure outside of AWS.
- Another feature of Route 53 is the ability to manage the DNS records for domain names. You can register new domain names directly in Route 53. You can also transfer DNS records for existing domain names managed by other domain registrars. This enables you to manage all of your domain names within a single location.
-  Route 53 can direct traffic to different endpoints using several different routing policies, such as latency-based routing, geolocation DNS, geoproximity, and weighted round robin. If we take geolocation DNS, that means we direct traffic based on where the customer is located
### Example How Amazon Route 53 and Amazon CloudFront deliver content:
- Suppose that AnyCompany’s application is running on several Amazon EC2 instances. These instances are in an Auto Scaling group that attaches to an Application Load Balancer. 

   - A customer requests data from the application by going to AnyCompany’s website. 
   - Amazon Route 53 uses DNS resolution to identify AnyCompany.com’s corresponding IP address, 192.0.2.0. This information is sent back to the customer. 
   - The customer’s request is sent to the nearest edge location through Amazon CloudFront. 
   - Amazon CloudFront connects to the Application Load Balancer, which sends the incoming packet to an Amazon EC2 instance.

<img width="840" alt="e-xAJkcMGrxL3sq4_WE71CA369xcdceJ2" src="https://github.com/Ragdha-Elgaidi/Cloud-Essentials-Learning-Plan/assets/76912120/bb0d7ea4-1a25-45aa-85c0-4a0ed057c278">
#####  CDN is a network that helps to deliver edge content to users based on their geographic location. 
