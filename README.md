# terraform-azurerm-os-calculator
[Heavily inspired form Terraform Azure Compute Module](https://github.com/Azure/terraform-azurerm-compute)

Designed to be used with Libre DevOps VM modules, and will simplify the way of getting SKUs for your VM images without having to look it up.

Simple pass the OS you want to the variable, and it will output the values of the publisher, offer and SKU.  All versions are latest

```hcl
module "os_calculator" {
  source = "github.com/libre-devops/terraform-azurerm-win-os-sku-calculator"

  vm_os_simple = "Debian" // will give you WindowsServer2019 sku properties, to be used in windows-vm module
}
```
## Requirements

No requirements.

## Providers

No providers.

## Modules

No modules.

## Resources

No resources.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_standard_os"></a> [standard\_os](#input\_standard\_os) | Definition of the standard OS with "SimpleName" = "publisher,offer,sku", this can have many more skus added to it | `map` | <pre>{<br>  "Windows10": "MicrosoftWindowsDesktop,Windows-10,win10-21h2-ent-ltsc",<br>  "Windows11": "MicrosoftWindowsDesktop,Windows-11,win11-21h2-ent",<br>  "WindowsServer2008": "MicrosoftWindowsServer,WindowsServer,2008-R2-SP1",<br>  "WindowsServer2012": "MicrosoftWindowsServer,WindowsServer,2012-Datacenter",<br>  "WindowsServer2016": "MicrosoftWindowsServer,WindowsServer,2012-Datacenter",<br>  "WindowsServer2019": "MicrosoftWindowsServer,WindowsServer,2019-Datacenter",<br>  "WindowsServer2019WithContainers": "MicrosoftWindowsServer,WindowsServer,2019-Datacenter-with-Containers",<br>  "WindowsServer2022": "MicrosoftWindowsServer,WindowsServer,2022-Datacenter",<br>  "WindowsServerAzureEdition": "MicrosoftWindowsServer,WindowsServer,2022-datacenter-azure-edition"<br>}</pre> | no |
| <a name="input_vm_os_simple"></a> [vm\_os\_simple](#input\_vm\_os\_simple) | n/a | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_calculated_value_os_offer"></a> [calculated\_value\_os\_offer](#output\_calculated\_value\_os\_offer) | Gets the offer value |
| <a name="output_calculated_value_os_publisher"></a> [calculated\_value\_os\_publisher](#output\_calculated\_value\_os\_publisher) | Gets the offer value |
| <a name="output_calculated_value_os_sku"></a> [calculated\_value\_os\_sku](#output\_calculated\_value\_os\_sku) | Gets the OS value |