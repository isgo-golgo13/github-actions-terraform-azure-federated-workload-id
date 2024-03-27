# Terraform Azure AD Workload Identity Federation (Root) Module for GitHub Actions Workflow 

This root Terraform module will call 
`https://github.com/isgo-golgo13/terraform-azuread-workload-id-federation-github-actions.git`. This child module provisions Azure AD App Registration (Azure AD Service Principal) and OIDC Azure AD Federated Credentials from the Azure AD App Registration Service Principal. 

## Sources

Refer to the following documentation on GitHub and Azure AD for using the federated identity with GitHub Actions:

### Authenticate from Azure to GitHub 
- https://docs.microsoft.com/en-us/azure/developer/github/connect-from-azure

### Configuring Open ID Connect in Azure
- https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-azure
