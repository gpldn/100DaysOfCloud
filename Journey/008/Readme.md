**Add a cover photo like:**
![VNets](https://user-images.githubusercontent.com/53405071/106384145-7b18e880-63c1-11eb-8399-cf7e71af5de1.png)

# Planning virtual networks

## Introduction
I began to struggle with the simple consumption of documentation, so thought I would check out the #100DaysOfCloudIdeas repository. This particular challenge seemed like a good place to start for me. It's a nice change to of object orientated tasks than just reading. I liked that this particular challenge requires some thought, rather than copying what I'm seeing into Notion and re-reading later on.

I like the "active-recall" style(ish) of this task. I'm reading the documentation, being asked a question, thinking about the question, and then presenting an answer. Whilst I will 100% have to run through these again at some point, it just helps solidify that information even more.

## Prerequisite

It would be a good idea to have some knowledge of the following before attempting the lab:
• CIDR notations
• Subnets
• Virtual networks

## Use Case

Virtual Networks are one of the backbones of Microsoft Azure. It's one of the fundamentals which everyone should have an understanding of. 

## Cloud Research

As per the lab goals, by the end of this session I need to be able to provide an answer to the following questions:
•	How many IP addresses does Azure hold per subnet?
•	What is the smallest IP address range you can specify for an Azure subnet?
•	In this IP range 10.1.0.0/29 what does the number after the slash represent?
•	Can a subnet be deleted from a virtual network?
•	Can changes be made to an IP address range?
•	What are some considerations that help you determine how many virtual networks and subnets you require?

**How many IP addresses does Azure hold per subnet?**
Azure holds 5 IP addresses per subnet. This means if you are using 10.0.0.0/24 you will only be able to use 251 of the available 256 IP addresses.

**What is the smallest IP address range you can specify for an Azure subnet?**
The smallest address range you can specify in Azure is the /29 range. This is because the /29 range will provide you with 8 IP addresses. As we know, Azure reserves 5 of those addresses, leaving us with only 3 that we can use.

**In this IP range 10.1.0.0/29 what does the number after the slash represent?**
This number represents the bit mask of the network. It tells us how many bits are the same for each IP on the subnet, and which are are variable. An IP address is made up of 32 bits, which is split into 4 octets. Each octet has 8 bits.

**an a subnet be deleted from a virtual network?**
A subnet can only be deleted from a virtual network if the subnet is empty.

**Can changes be made to an IP address range?**
Yes, changes can be made, but only when there are no devices connected to the subnet. 

**What are some considerations that help you determine how many virtual networks and subnets you require?**
Do some of our organisational requirements mean that we need to isolate traffic to separate virtual networks? If the virtual network needs to communicate with other networks, we could put an appliance such as a firewall in front of it. This will allow us to control the traffic flow between virtual networks whilst keeping it secure.

Do we have any requirements which might mean our virtunal networks need to be in separate subscriptions or regions? This could be for billing purposes, or we could have multiple offices globally which would require resources to be in X location for latency reasons. It could also be for data security, such as GDPR reasoning.

How many NICs and private IPs do we require within the virtual network? Does this exceed the limit that you can have within a virtual network?

Will we need to connect the virtual network to another virtual network, or an on-premises network? If so, we need to make sure that each network has a unique address space and that there is no overlap. For example, we could not have both of our virtual network and on-premises network on 10.0.0.0/.

Do we require resources to be part of different virtual networks to simplify permission assignments? Different policies can be assigned to different virtual networks for ease of management. 

When we deploy some Azure resources, they will also deploy their own virtual networks. 
