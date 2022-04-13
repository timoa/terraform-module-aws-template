# Terraform module template

A Terraform module uses as a template to start new module.

It includes all the automation (versioning, providers update, lint, security) and best practices from HashiCorp.

## Usage

### Integrate the module into your Terraform project

If you want to use this module inside your project, you can use the following code (change the tag to match the latest version):

```bash
module "module-template" {
  source = "git::https://github.com/timoa/terraform-module-aws-template.git?ref=tags/0.0.2"

  # Required
  region    = "us-east-1"

  # Optional
  namespace = "my-project"
  stage     = "prod"
}
```

### Output example

```bash
terraform init
terraform plan
```

```bash
Changes to Outputs:
  + available_zones = [
      + "us-east-1a",
      + "us-east-1b",
      + "us-east-1c",
      + "us-east-1d",
      + "us-east-1e",
      + "us-east-1f",
    ]

You can apply this plan to save these new output values to the Terraform
state, without changing any real infrastructure.
```

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.0 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | 4.9.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | 4.9.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_availability_zones.available](https://registry.terraform.io/providers/hashicorp/aws/4.9.0/docs/data-sources/availability_zones) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_namespace"></a> [namespace](#input\_namespace) | Project name that will be use to identifiy the resources | `string` | `"my-project"` | no |
| <a name="input_region"></a> [region](#input\_region) | Default Region | `string` | `"us-east-1"` | no |
| <a name="input_stage"></a> [stage](#input\_stage) | Stage/environment name to tag and suffix the infrastructure composants | `string` | `"dev"` | no |
| <a name="input_tags"></a> [tags](#input\_tags) | Default tags to associate to these resources | `map(string)` | <pre>{<br>  "BusinessUnit": "My Company",<br>  "Team": "DevOps",<br>  "Terraform": "true"<br>}</pre> | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_available_zones"></a> [available\_zones](#output\_available\_zones) | Return the list of available zones |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
