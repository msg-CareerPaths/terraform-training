# Input Variables

Variables helps the ability to customize the functionality of the code without directly altering.

## Reading 

- [Input Variables](https://developer.hashicorp.com/terraform/language/values/variables)
- [Local Variables](https://developer.hashicorp.com/terraform/language/values/locals)
- [Setting environment variables using .tfvars](https://spacelift.io/blog/terraform-tfvars)
- [Protect Sensitive Input Variables](https://developer.hashicorp.com/terraform/tutorials/configuration-language/sensitive-variables)

## Practical Work

- Create a new file called `variables.tf` and inside it
  - Create a variable of type string which will represent the path to the previously created file
  - Create a variable for the key of the file
  - Create a variable for the name of the bucket
- Use them inside the `s3.tf` instead of the hard-coded strings
- Provide them through a `terraform.tfvars` file
- Apply the changes (destroy the previous created resources) and test that it works