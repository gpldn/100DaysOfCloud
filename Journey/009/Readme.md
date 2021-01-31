![VNet Peering](https://user-images.githubusercontent.com/53405071/106398364-467d4f00-640a-11eb-98a6-895fb396bff8.png)

# Connecting VNets with VNet Peering

## Introduction

I thought it made sense to carry on where I left of with the network work. This time some actual lab work was in order. 

## Prerequisite

Before doing this, you should understand what a VNet is, and how IP address ranges work. 

## Use Case

You would use VNet Peering when you need to connect one VNet to another. An example of this would be that your resources in one location need to communicate with resources in another location. For my example I have chosen to connect the London and Madrid offices. 

## Cloud Research

I was able to do this mostly from memory thanks to Scott Duffy's AZ-104 course on Udemy. I did run into a very small problem with not knowing that I needed to allow ICMP in order to ping the resources. I assumed this was enabled by default.

**What is VNet peering?**
VNet Peering allows you to connect multiple VNets. This means your resources can communicate with eachother, even if they are in a different VNet. Your VNets do not need to be in the same region.

**What are some limitations of VNet peering?**
* You cannot peer across clouds.
* You cannot add/delete address ranges to/from a VNet's address space once it has been peered with another VNet. If you have to do this, you must delete the peering, make the changes, and then recreate the peering.
* VNet Peerings are not transitive. If you've set up peering from VNet 1 to 2 and from VNet 2 to 3, VNet 3 will not be able to communicate with VNet 1. You can configure this though.

**What is the difference between VNet peering and VPN Gateway?**
VNet Peering allows us to connect VNets within Azure. All traffic through the peering is using Microsoft's backbone, which provides a low latency, high bandwidth connection. It also means that your traffic does not cross over the public internet.

VPN Gateways allow us to connect our VNets to our on-premises networks over the public internet. A VPN Gateway can also be used to send traffic between VNets, but there are specific use cases for this. 
