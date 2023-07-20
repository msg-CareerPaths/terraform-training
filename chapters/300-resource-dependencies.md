# Resource Dependencies 

Resource must be created in a certain order based on certain dependencies. 
These are called implicit dependencies, and they exist when another resource reference the other. 
Terraform tries to create an order of which resource should be created first. 
In case it does not always succeed, there are explicit dependencies which uses the `depends_on` parameter. 

## Reading

- [Resource Dependency](https://developer.hashicorp.com/terraform/tutorials/configuration-language/dependencies)


## Practical Work

- Create a folder inside your repository called `s3-assets/`
  - Create a new file `my-first-file.txt` and populate it
- Add a new resource inside your `s3.tf` called [aws_s3_object](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_object)
  - Add as key the name of the file `my-first-file`
  - For the bucket parameter, you will need to reference as dependency your bucket id `aws_s3_bucket.tt-bucket.id`
  - For the source the path to the file based on current module `"${path.module}/assets/first-file.txt"`
- Run `terraform apply` (or `tflocal apply`) and approve
- To check the file was added you can do the following:
  - Run `<aws / awslocal> s3api list-objects --bucket tt-bucket` to list all the bucket files
  - Run `<aws / awslocal> s3api get-object --bucket tt-bucket --key my-first-file output-file.txt` to download the file