# Terraform, Azure and Azure AD Workload Identity Federation Module for GitHub Actions
Terraform module to create an Azure AD application, service principal, and federated identity for GitHub-based OIDC authentication.

Creates the following resources:

- Azure AD application (azuread_application)
- Federated Identity Credential (azuread_application_federated_identity_credential)
- Azure AD Service Principal (azuread_service_principal)

The output from the module is the full azuread_service_principal object, since you may need access to all or some of the attributes like `object_id`, `application_id`, or `application_tenant_id`.

The module provides GitHub Actions OIDC authentication for Azure AD.

## Module Reference

```
module "nonprod_env" {
    source           = "isgo-golgo13/terraform-azure-workload-identity-federation-github-actions"
    version          = "1.0"

    identity_name    = "github-actions-azad-azfedid-oidc"
    repository_name  = "isgo-golgo13/"
    entity_type      = "environment"
    environment_type = "nonprod"
}

output "service_principal" {
  value = module.nonprod_env.service_principal
}
```

## Sources

Refer to the following documentation on GitHub and Azure AD for using the federated identity with GitHub Actions:

### Authenticate from Azure to GitHub 
- https://docs.microsoft.com/en-us/azure/developer/github/connect-from-azure

### Configuring Open ID Connect in Azure
- https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-azure
