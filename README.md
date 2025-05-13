
# TF-google-workstation

This Terraform module provisions a fully managed [Google Cloud Workstations](https://cloud.google.com/workstations) environment, enabling secure, scalable, and customizable development workspaces in the cloud. Also, I used this module to experiment with `terraform-docs`.

---

## 🚀 Features

- **Automated Provisioning**: Deploys a complete Cloud Workstation setup, including clusters, configurations, and instances.
- **Customizable Configurations**: Supports custom Docker images and startup scripts for tailored development environments.
- **Secure Networking**: Configures VPCs, subnets, and firewall rules to ensure secure access.
- **IAM Integration**: Manages IAM roles and permissions for fine-grained access control.
- **Artifact Registry Support**: Integrates with Google Artifact Registry for storing and retrieving custom images.
- **Automated Documentation**: Utilizes `terraform-docs` with pre-commit hooks and GitHub Actions to maintain up-to-date module documentation.

---

## 📁 Module Structure

- `main.tf`: Primary module configuration.
- `variables.tf`: Input variable definitions.
- `network.tf`: VPC and subnet configurations.
- `firewall.tf`: Firewall rule definitions.
- `iam.tf`: IAM roles and bindings.
- `artifact.tf`: Artifact Registry setup.
- `workstation.tf`: Workstation cluster and configuration resources.
- `provider.tf`: Provider configurations.
- `workstation-setup.sh`: Startup script for workstation customization.
- `.terraform-docs.yml`: Configuration for `terraform-docs`.
- `.pre-commit-config.yaml`: Pre-commit hook configurations.
- `.github/workflows/terraform-docs.yaml`: GitHub Actions workflow for documentation automation.

---

## 🛠️ Usage

```hcl
module "cloud_workstation" {
  source  = "github.com/khoubate/TF-gcp-workstation"
  
  project_id       = "your-gcp-project-id"
  region           = "us-east1"
  network_name     = "your-vpc-network"
  subnet_name      = "your-subnet"
  workstation_name = "dev-workstation"
  
  # Optional configurations
  custom_image     = "gcr.io/your-project/custom-image:tag"
  startup_script   = file("workstation-setup.sh")
}
```

---

## 📌 Requirements

- **Terraform**: v1.0 or higher
- **Google Cloud Provider**: v4.0 or higher
- **Enabled APIs**:
  - `cloudresourcemanager.googleapis.com`
  - `compute.googleapis.com`
  - `workstations.googleapis.com`
  - `artifactregistry.googleapis.com`

---

## 🔧 Inputs

| Name             | Description                          | Type   | Default | Required |
|------------------|--------------------------------------|--------|---------|:--------:|
| `project_id`     | GCP project ID                       | string | n/a     |   yes    |
| `region`         | GCP region for resources             | string | n/a     |   yes    |
| `network_name`   | Name of the VPC network              | string | n/a     |   yes    |
| `subnet_name`    | Name of the subnet                   | string | n/a     |   yes    |
| `workstation_name` | Name of the workstation instance   | string | n/a     |   yes    |
| `custom_image`   | Custom Docker image for the workstation | string | null    |    no    |
| `startup_script` | Path to the startup script           | string | null    |    no    |

---

## 📤 Outputs

| Name                  | Description                                |
|-----------------------|--------------------------------------------|
| `workstation_id`      | ID of the created workstation              |
| `workstation_endpoint`| Access URL for the workstation             |
| `artifact_registry`   | Name of the Artifact Registry repository   |

---

## 📄 Documentation Automation

This module leverages [`terraform-docs`](https://terraform-docs.io/) for automated documentation generation.

### Pre-commit Hook

1. **Install Pre-commit**:

   ```bash
   pip install pre-commit
   ```

2. **Install Git Hooks**:

   ```bash
   pre-commit install
   ```

This setup ensures that documentation is automatically updated before each commit.

### GitHub Actions

A GitHub Actions workflow (`.github/workflows/terraform-docs.yaml`) is configured to automatically update the documentation on pushes and pull requests to the `main` branch.

---

## 📚 References

- [Google Cloud Workstations Documentation](https://cloud.google.com/workstations/docs)
- [terraform-docs Documentation](https://terraform-docs.io/)
- [Automating Terraform Documentation](https://blog.devops.dev/no-one-should-write-terraform-documentation-manually-16ebf22b6368)

---

## 🧾 Terraform Documentation sample

You can check the documentation of this project using `terraform-docs` here: [`terraform-docs`](TF-docs.md).

---

For more information and best practices on structuring Terraform modules and documentation, refer to the [Terraform Module Standards](https://cloud.google.com/docs/terraform/best-practices/general-style-structure).
