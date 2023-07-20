# Description

Terraform is HashiCorp's infrastructure as code tool. It lets you define resources and infrastructure in human-readable, declarative configuration files, and manages your infrastructure's lifecycle.
Terraform has several plugins called providers which interacts with various cloud providers API's (AWS, Azure, GCP, etc.) to create/manage/destroy infrastructure resources.


# Working Mode

All the code written must be published on GitHub
- Create your own repository on your personal account and give access to your mentor (make sure you specify your name in case you have an esoteric username).
- Commits must be pushed when each individual chapter is finished.
- [Create](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository) a `develop` branch from the `master` branch **before starting work**.
- **In order to request a code review from the mentors**, you must [open a pull request](https://help.github.com/en/articles/creating-a-pull-request) from the `develop` to the `master` branch. Inform them in your **daily standup** of this or through a PM.
- **Once the Pull Request is approved** by the mentors, merge it into `main` and create another branch from master to continue work.
- Take care to delete your `develop` branch then, go back inside your IDE to `main` and update it (git pull)
- Carry on your work by creating another `develop` branch and working on it
- Repeat ad infinitum (until the training has ended)

# Environment Setup

On your local machine install the following:
- Install [Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli?in=terraform%2Faws-get-started).
- Install [Python](https://www.python.org/downloads/)
- Install [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- Install [Docker](https://medium.com/geekculture/run-docker-in-windows-10-11-wsl-without-docker-desktop-a2a7eb90556d)
  - Open a terminal in this repository `setup/` folder and run a `docker-compose up -d`
- This training will not consist on actually creating resources on a cloud provider specifically, therefore we will use some wrappers and create resources in a mock environment called [LocalStack](https://docs.localstack.cloud/overview/):
  - Install a Terraform wrapper for LocalStack by running `pip install terraform-local` in a terminal
  - Install a AWS CLI wrapper for LocalStack by running `pip install awscli-local` in a terminal
  - Test the installation by running `tflocal --help` and `awslocal s3api list-buckets`
- Install an IDE (VSCode/Webstorm) with support through plugins for HCL (Terraform Code)

# Difference between Wrappers and Normal Commands

- When running commands through the wrappers the only difference is that it will run those commands against the local network (localhost instead of AWS Cloud).
- When using **Terraform**, if you are using LocalStack run `tflocal <command>` instead of `terraform <command>`
- When using **AWS CLI**, if you are using LocalStack run `awslocal <command>` instead of `aws <command>`