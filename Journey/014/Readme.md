![OpenHack](https://user-images.githubusercontent.com/53405071/107161942-e8b3ae80-6997-11eb-8616-1de6927dab77.png)

# Microsoft OpenHack: Migrating Workloads to Azure – Day 1

Day 1 of the OpenHack went pretty well. It was quite tough for me to understand some concepts, but I think I kept up with it for the most part.

In the morning we were presented with the task at hand. In short, we need to assess, migrate, modernise and optimise existing on-premises applications hosted in Windows Server 2008 R2 and Microsoft SQL Server 2008 R2 as they move to Azure.

**Challenge 1: Establish your plan**

Our first challenge was to begin planning for the initial migration of the client's applications and infrastructure to Azure. 

We discussed amongst ourselves and came to a conclusion on what the architecture would look like once in Azure. We created a very, very rough drawing in Microsoft Whiteboard. None of us had Visio to hand unfortunately.

Once we hashed out the above, we looked through the reference articles provided by Microsoft. We decided that we would use Azure Migrate for assessing our workloads. Azure Migrate would show us if there are any server dependencies, and provide us with a rough cost estimate.

For our naming conventions, we went with the recommended convention from Microsoft. An example would be pip-webapp-prod-westus-001. This way we can tell what the resource type is, what workload/app it is, the type of environment, the region, and the instance number.

**Challenge 2: Assess workloads for migration**

The next challenge was to assess or workloads. As discussed, we planned on using Azure Migrate to do this. 

We began by preparing and configuring our Hyper-V host. In our case, we followed through the Microsoft instructions found [here](https://docs.microsoft.com/en-gb/azure/migrate/tutorial-discover-hyper-v#prepare-hyper-v-hosts).

Once this was done it was time to assess our servers. Again, we followed the Microsoft documentation [here](https://docs.microsoft.com/en-gb/azure/migrate/tutorial-assess-hyper-v) to do this. From the assessment we hoped to gain the following insights of our workload:
* Azure readiness
* Azure sizing
* Cost estimation
* Dependency analysis

At the end of this exercise we left our assessment running overnight to return to tomorrow!
