# Managing State

## Reading

- [Backend](https://developer.hashicorp.com/terraform/language/settings/backends/configuration)
- [Backend on S3](https://developer.hashicorp.com/terraform/language/settings/backends/s3)
- [Remote State on S3](https://medium.com/dnx-labs/terraform-remote-states-in-s3-d74edd24a2c4)
- [Mutable vs Immutable Infrastructure](https://www.hashicorp.com/resources/what-is-mutable-vs-immutable-infrastructure)

## Practical Work

For this part we will switch completely from working with LocalStack to fully working on AWS.

### Prerequisites

- Have an AWS account with a IAM user with programmatic keys and administrator access.
- Configure the aws cli locally using `aws configure` on region `eu-central-1` and add the access keys

1. Create a s3 bucket by hand through the AWS console which the following name `<your-aws-account-id>-terraform-training-infra`
2. Add to your `main.tf` file a backend for s3 which references the previously created bucket
3. Run the terraform pipeline and validate your resources