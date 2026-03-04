# Terraform EIP Module

This module creates an External Compute Address resource on Google Cloud Platform.

## Prerequisites

Below prerequisites must be fulfilled for successful execution of terraform concept code sets.

### Software Requirement

Resources in this repository are meant to use with Terraform 1.14.0 (check the terraform version using: `terraform version`). If you don't have the compatible version, download it from official Terraform repository.

- [Terraform](https://www.terraform.io/downloads.html) >= 1.14.0
- [Terraform Provider for GCP](https://github.com/terraform-providers/terraform-provider-google) >= 7.21.0
- [Terraform Provider for GCP Beta](https://github.com/terraform-providers/terraform-provider-google-beta) >= 7.21.0
- [gcloud](https://cloud.google.com/sdk/gcloud/) > 548.0.0

> **Note:**
> See [Installation-Guide](https://gist.github.com/oneanupam/7458df6506e8e3cfb28c0ff56fab546a) on how to install Terraform.

### API Requirement

In order to deploy the VPC using this module, you must activate the Compute Engine API on the project.

- Compute Engine API - compute.googleapis.com

## Example Usage

```bash
module "example-eip" {
  source = "oneanupam/eip/google"

  project      = var.project_id
  name         = var.address_name
  address_type = "EXTERNAL"
  region       = var.region
  network_tier = var.network_tier
}
```

Then perform the following commands on the root folder:

- [Required] `terraform init` # To initialize the terraform working directory.
- [Optional] `terraform validate` # To validate the terraform configuration.
- [Optional] `terraform fmt` # To format the terraform configuration to a canonical format and style.
- [Optional] `terraform plan` # To create an execution plan for terraform configuration files.
- [Required] `terraform apply -auto-approve` # To execute the actions proposed in a terraform plan to create, update, or destroy infrastructure.
- [Optional] `terraform destroy -auto-approve` # To destroy the created infrastructure. Specific resources can be destroyed using resource targeting.

## Testing

Unit testing and Integration testing for terraform modules can be done using terraform testing framework. This terraform module uses terraform test.

```bash
    `terraform test` # runs the test cases sequentially
```
