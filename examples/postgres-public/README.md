# Cloud SQL Database Example

This example shows how to create the public Postgres Cloud SQL database using the Terraform module.

## Run Terraform

Create resources with terraform:

```bash
terraform init
terraform plan
terraform apply
```

To remove all resources created by terraform:

```bash
terraform destroy
```

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| authorized\_networks | List of mapped public networks authorized to access to the instances. Default - short range of GCP health-checkers IPs | list(map(string)) | `<list>` | no |
| db\_name | The name of the SQL Database instance | string | `"example-postgres-public"` | no |
| project\_id | The ID of the project in which resources will be provisioned. | string | `"null"` | no |

## Outputs

| Name | Description |
|------|-------------|
| database\_version | The Postgres version to use. |
| name | The name for Cloud SQL instance |
| project\_id | The project to run tests against |
| psql\_conn | The connection name of the master instance to be used in connection strings |
| psql\_user\_pass | The password for the default user. If not set, a random one will be generated and available in the generated_user_password output variable. |
| public\_ip\_address | The first public (PRIMARY) IPv4 address assigned for the master instance |
| region | The region of the Cloud SQL resources |
| tier | The tier for the master instance. |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->