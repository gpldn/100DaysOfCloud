# Azure AD Identity Design

## Cloud Research

### Hybrid Authentication

When thinking about identity design, we need to understand how we are going to set this up. Will our client be using Azure AD alone, or will they have their authentication on-premises? 

In most cases, there will be a hybrid solution where there is a requirement for SSO, but authentication is managed on-prem. In this scenario, we would link Azure AD with the on-premises AD using Azure AD Connect. 

Azure AD Connect is a synchronisation service which syncs our objects from on-prem to the cloud.

You can't do hybrid identity using the .onmicrosoft domain.

To do "High Availability" with Azure AD you would but AD Connect on another server in staging mode. The service would run and observe the service running on the primary server. Once the primary comes offline, the secondary would take over. 

### Authentication Considerations

Do our clients need to be able to reset their own passwords? If so, we should enable self-service password reset (SSPR). This is a free service provided by Microsoft.

Do our clients have the need to be able to write back these passwords from the cloud to on-prem? If so, they will require at least an Azure P1 license. 

Do our clients require further authentication security? Realistically, all clients should have MFA enabled. 

Do our clients *only* require specific users to have MFA enabled? If so, we can use tools such as Conditional Access to create policies which specify who needs additional authentication depending on location, device status, and what groups they may be in. A P1 license is required for this.

Is Azure Identity Protection required? This uses AI to determine risky sign-ins depending on a number of conditions e.g. sign-in location, unusual activity. If users reach the threshold you can determine the user risk policy to set actions e.g. change your password. Azure Identity Protection is an Azure AD P2 license feature.

Will we be using Password Hash Synchronisation or Pass-through Authentication?

- Password Hash Synchronisation
    - Password hashes are replicated/copied to Azure AD (a hash of a hash in this scenario)
    - Operate over the web service ports 443 and 80
    - Even if Azure AD Connect is interrupted, users will still be able to log into cloud apps
- Pass-through Authentication
    - Replicates users, but not the passwords to Azure AD
    - If something interrupts the Azure AD Connect service, users won't be able to log into cloud apps
    - More-so for compliance
