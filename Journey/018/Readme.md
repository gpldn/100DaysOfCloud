![Cost Management + Billing](https://user-images.githubusercontent.com/53405071/107997330-6dc34700-6fda-11eb-9a6c-e2de0a50a7d4.png)

# Creating Cost Alerts

## Introduction

In today's session, I will be creating 2 different types of cost alerts in Azure. My aim is to be able to answer the following questions by the end:

* What is the difference between a Budget Alert and a Credit Alert?
* What is the cost for creating Cost Alerts?
* When a cost alert is triggered how will you know?
* Under what service in the Azure Portal do you find Cost Alerts?

## Use Case

Cost management is an essential in Azure, or any other cloud service for that matter. It's imperative we know how much we are spending, and on what. One of the most attractive benefits of the cloud is the cost saving potential, so we need to be sure are actually saving money and not going over budget.

## Cloud Research

I got the idea for this from the #100DaysOfCloud repo ![here](https://github.com/100DaysOfCloud/100DaysOfCloudIdeas/blob/master/Projects/BIL/BIL01/BIL01-AZ100.md). Materials I referenced along the way are as follows:
* ![Use cost alerts to monitor usage and spending](https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/cost-mgt-alerts-monitor-usage-spending)
* ![Create and manage Azure budgets](https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets)

## ☁️ Cloud Outcome
**What is the difference between a Budget Alert and a Credit Alert?**
A budget alert can be used to create both cost-based alerts and consumption-based alerts. You can define who receives these alerts in the alerts recipients list.

Credit Alerts are for when your Azure Prepayment is almost consumed. It will alert you once you've used 90% of the budget, and again at 100%. The account owners will receive these alerts. This is also only available for those with an Enterprise Agreement.

**What is the cost for creating Cost Alerts?**
As far as I understand, creating these alerts are free. However, calling on the action groups can cost depending on the type of action is called upon.

**When a cost alert is triggered how will you know?**
This depends on how you have set up the alert. You can be notified via e-mail, and you can also call upon action groups which trigger specific actions.

**Under what service in the Azure Portal do you find Cost Alerts?**
Cost Management + Billing

## Next Steps

✍️ Describe what you think you think you want to do next.
