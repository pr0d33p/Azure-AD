# Azure Active Directory (Azure AD) Terminology

## Tenant
An instance of Azure AD representing a single organization.

## Azure AD Directory
Each tenant has a dedicated Directory for identity and access management.

## Subscriptions
Used to pay for services in Azure. Multiple subscriptions can exist in a Directory.

## Core Domain
The initial domain name (.onmicrosoft.com) for a tenant. Custom domain names can also be defined.

---

## Azure Resource Hierarchy

### Management Groups
- Used to manage multiple subscriptions.
- Inherited conditions apply to all subscriptions within a management group.
- All subscriptions in a management group belong to the same tenant.
- Can be nested hierarchically.

### Subscriptions
- Logical units of Azure services linked to Azure accounts.
- Billing and access control boundaries in Azure AD.
- A subscription trusts only one directory.
- Roles applied at this level affect all resources in the subscription.

### Resource Groups
- Containers for Azure resources.
- All resources must belong to a resource group.
- Deleting a group deletes all resources within.
- Have their own Identity and Access Management (IAM) settings.

### Resources
- Deployable items in Azure like VMs, App Services, Storage Accounts, etc.

---

## Managed Identity
- Assigned to Azure resources like app service, function apps, virtual machines, etc.
- Uses Azure AD tokens for authentication to access other resources.

## Azure Resource Manager (ARM)
- Deployment and management service for Azure.
- Used for lifecycle management and access control of resources.
- ARM templates ensure consistent and dependency-defined redeployment.

---

## Azure RBAC Roles
- **Owner:** Full access to resources, can manage access for others.
- **Contributor:** Full access, cannot manage access.
- **Reader:** View resources.
- **User Access Administrator:** View and manage access for others.

## Azure AD Roles
- **Global Administrator:** Most powerful admin role, can elevate to User Access Administrator.
- **Default User Permissions:** Includes various permissions in Azure AD.

---

## Tokens
OAuth 2.0 and OIDC use bearer tokens:
- **Access Tokens:** Used by clients to access resources, specific to user, client, and resource.
- **ID Tokens:** Basic user information token, specific to user and client.
- **Refresh Tokens:** Used to get new access and ID tokens, can be revoked.
