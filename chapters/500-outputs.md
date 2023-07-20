# Outputs

Represent a way to expose information about the infrastructure for later use.

## Reading

- [Output Values](https://developer.hashicorp.com/terraform/language/values/outputs)

## Practical Work

- Create a new file called `outputs.tf`
- Inside create an output variable `tt_bucket_arn`
    ```hcl
    output "tt_bucket_arn" {
      value = aws_s3_bucket.tt-bucket.arn
    }
    ```
- Apply infrastructure changes and watch for the output
- Change the variable to be sensitive
    ```hcl
    output "tt_bucket_arn" {
      value = aws_s3_bucket.tt-bucket.arn
      sensitive = true
    }
    ```
- Apply changes and watch the output
- To see the value now run inside a terminal `<terraform / tflocal> output tt_bucket_arn`