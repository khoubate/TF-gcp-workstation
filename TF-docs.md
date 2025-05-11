This desmostarte how we can automate Terraform documentation by using `terraform-docs`.

<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_google"></a> [google](#provider\_google) | n/a |
| <a name="provider_google-beta"></a> [google-beta](#provider\_google-beta) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [google-beta_google_workstations_workstation.default](https://registry.terraform.io/providers/hashicorp/google-beta/latest/docs/resources/google_workstations_workstation) | resource |
| [google-beta_google_workstations_workstation_cluster.default](https://registry.terraform.io/providers/hashicorp/google-beta/latest/docs/resources/google_workstations_workstation_cluster) | resource |
| [google-beta_google_workstations_workstation_config.default](https://registry.terraform.io/providers/hashicorp/google-beta/latest/docs/resources/google_workstations_workstation_config) | resource |
| [google-beta_google_workstations_workstation_iam_member.member](https://registry.terraform.io/providers/hashicorp/google-beta/latest/docs/resources/google_workstations_workstation_iam_member) | resource |
| [google_artifact_registry_repository.workstation-repo](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/artifact_registry_repository) | resource |
| [google_compute_firewall.workstation-egress](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_firewall) | resource |
| [google_compute_firewall.workstation-ingress](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_firewall) | resource |
| [google_compute_network.main-vpc](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_network) | resource |
| [google_compute_subnetwork.main-subnet](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_subnetwork) | resource |
| [google_project_iam_member.workstation-image](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/project_iam_member) | resource |
| [google_project_service.api](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/project_service) | resource |
| [google_service_account.image-pull](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/service_account) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_artifact_repo"></a> [artifact\_repo](#input\_artifact\_repo) | n/a | `string` | n/a | yes |
| <a name="input_project_id"></a> [project\_id](#input\_project\_id) | n/a | `string` | n/a | yes |
| <a name="input_region"></a> [region](#input\_region) | n/a | `string` | n/a | yes |
| <a name="input_subnetwork_name"></a> [subnetwork\_name](#input\_subnetwork\_name) | n/a | `string` | n/a | yes |
| <a name="input_subnetwork_range"></a> [subnetwork\_range](#input\_subnetwork\_range) | n/a | `string` | n/a | yes |
| <a name="input_vpc_name"></a> [vpc\_name](#input\_vpc\_name) | n/a | `string` | n/a | yes |

## Outputs

No outputs.
<!-- END_TF_DOCS -->