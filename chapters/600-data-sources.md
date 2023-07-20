# Data Sources

They allow you to access infrastructure data which was defined outside your terraform code.

## Reading

- [Data Sources](https://developer.hashicorp.com/terraform/language/data-sources)

## Practical Work

- Create a resource through AWS CLI by running `<aws / awslocal> s3api create-bucket --bucket sample-bucket`
- Create a new file called `data-resources.tf` and add the following:
    ```hcl
    data "aws_s3_bucket" "sample_bucket" {
      bucket = "sample-bucket"
    }
    ```
- Modify the `outputs.tf` file and add an output variable for the reference bucket arn, use `data.aws_s3_bucket.sample_bucket.arn`