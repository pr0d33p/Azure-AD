# Recon Tools and Techniques for Azure AD

## Manual Reconnaissance

### Valid Emails
- Manually gather valid email addresses.
- Tools like Hunter.io or email harvesters can be used.

### Check Tenant Usage and Federation
- Determine if the tenant is in use and if federation (with Azure AD or O365) is enabled.
- Federation allows users to authenticate using on-premises credentials for cloud resources.

### Get Tenant ID
- Use the following URL to get the Tenant ID:
  `https://login.microsoftonline.com/<DOMAIN>/.well-known/openid-configuration`

## Automated Recon Tools

### AADInternals
- A PowerShell module for Azure AD reconnaissance.
- GitHub repository: [AADInternals](https://github.com/Gerenios/AADInternals)
- Usage:
  - Import the AADInternals module: `import-module .\AADInternals.psd1`
  - Get tenant information:
    - Login information: `Get-AADIntLoginInformation -UserName <RANDOM USER>@<DOMAIN>`
    - Tenant ID: `Get-AADIntTenantID -Domain <DOMAIN>`
    - Tenant domains: `Get-AADIntTenantDomains -Domain <DOMAIN>`
    - Comprehensive recon: `Invoke-AADIntReconAsOutsider -DomainName <DOMAIN>`

### MicroBurst
- A tool for enumerating Azure services and resources.
- GitHub repository: [MicroBurst](https://github.com/NetSPI/MicroBurst)
- Usage:
  - Enumerate used services: `Invoke-EnumerateAzureSubDomains -Base <SHORT DOMAIN NAME>`
  - Enumerate Azure blobs: `Invoke-EnumerateAzureBlobs -Base <SHORT DOMAIN> -OutputFile azureblobs.txt`

### o365creeper
- Tool for checking valid email IDs.
- GitHub repository: [o365creeper](https://github.com/LMGsec/o365creeper)
- Usage:
  - Check emails from a list: `python o365creeper.py -f list_of_emails.txt -o validemails.txt`
  - Try default email IDs like admin, root, test, contact.

### Additional Tools
- [OneDrive User Enum](https://github.com/nyxgeek/onedrive_user_enum): Enumerates OneDrive users (Non-lab-tool).
