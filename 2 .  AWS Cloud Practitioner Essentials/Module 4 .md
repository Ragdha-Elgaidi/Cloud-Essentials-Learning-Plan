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
- 
