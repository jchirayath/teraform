# teraform

A minimal **Terraform demo that provisions a Linux VM on Microsoft Azure**
(repo name is a typo for "terraform").

`LinuxVM.tf` uses the `azurerm` provider (~> 2.0) to create a complete,
self-contained example: resource group → virtual network → subnet → public IP →
network security group → NIC → Linux virtual machine (East US).

> Archival / personal demo (~2020, AzureRM provider 2.x). Pin/upgrade the
> provider version before reusing with current Terraform.

## Usage

```bash
# Authenticate to Azure (e.g. `az login` or service-principal env vars)
terraform init
terraform plan
terraform apply
...
terraform destroy   # tear everything down
```

Edit the hard-coded values in `LinuxVM.tf` (resource group name, location,
address spaces, VM size, admin credentials/SSH key) to suit your environment.

### Requirements

- [Terraform](https://www.terraform.io/)
- An Azure subscription and credentials (`az login` or
  `ARM_*` environment variables)
