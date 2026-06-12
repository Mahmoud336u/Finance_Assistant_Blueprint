# Dev Terraform Environment

Initialize Terraform with remote state backend settings:

```bash
terraform -chdir=infrastructure/terraform/envs/dev init -backend-config=backend.hcl.example
```

Then review and apply:

```bash
terraform -chdir=infrastructure/terraform/envs/dev plan
terraform -chdir=infrastructure/terraform/envs/dev apply
```
