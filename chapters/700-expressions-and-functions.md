# Expressions and Functions

## Reading

- [Expressions Overview](https://developer.hashicorp.com/terraform/language/expressions)
- [Functions Overview](https://developer.hashicorp.com/terraform/language/functions)
- [Manage Similar Resources with Count](https://developer.hashicorp.com/terraform/tutorials/configuration-language/count)
- [Manage Similar Resources with For Each](https://developer.hashicorp.com/terraform/tutorials/configuration-language/for-each)
- [Lifecycle Meta-Argument](https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle)

## Practical Work

- Add more files inside your `s3-assets` folder (at least 3)
- Modify the input variables so you instead of having 2 variables for one file key and path, you will have instead a map where the key is file key and the value is the file path
    ```hcl
    variable "file_assets" {
      type = map(string)
    }
    ```
- Make changes to your infrastructure code accordingly, so you upload to the bucket all those files (use `for_each`,`each.key` and `each.value`)
    ```hcl
      resource "aws_s3_object" "tt-bucket-files" {
        bucket = aws_s3_bucket.tt-bucket.id
        key    = each.key
        source = "${path.module}/${each.value}"
      
        for_each = var.file_assets
      }
    ```
- Apply the infrastructure and test the existence of the flies
