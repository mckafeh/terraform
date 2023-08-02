1.  Install yum-utils package
We’ll use yum-utils package that will help in adding HashiCorp repository to the system:

```
$ sudo yum install -y yum-utils
```

2. Next we add CentOS YUM repository

```
$ sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo
```
3. install 
```
sudo yum -y install terraform
```
4. AWS credentials
For Terraform to be able to make changes in your AWS account, you will
need to set the AWS credentials for the IAM user you created earlier as the
environment variables AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY

5. AWS CLI Configuration: First, ensure you have the AWS Command Line Interface (CLI) installed on your machine. If you don't have it installed, download and set it up with your AWS access keys by running aws configure. This will prompt you to enter your AWS Access Key ID and Secret Access Key, and you can optionally set the default region and output format.

Environment Variables: Terraform can use AWS credentials stored in environment variables. Check if you have the AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY environment variables set up correctly. You can set them in your terminal or shell script as follows:

```
$ export AWS_ACCESS_KEY_ID=(your access key id)
$ export AWS_SECRET_ACCESS_KEY=(your secret access key)

```

6. AWS Profile: If you have multiple AWS profiles set up, you can specify the profile to be used by Terraform by setting the AWS_PROFILE environment variable:
```
export AWS_PROFILE="your_profile_name"
```
Shared Credentials File: If you're using a shared credentials file (usually located at ~/.aws/credentials), ensure that it contains the correct AWS Access Key ID and Secret Access Key for the desired AWS profile.

IAM Role: If you're running Terraform on an AWS EC2 instance or another AWS service, make sure the instance or service has an IAM role attached with the necessary permissions. AWS will automatically provide temporary credentials to Terraform through the instance profile or service role.

Terraform Configuration: Double-check your Terraform configuration files (e.g., provider "aws" { ... }) to ensure that you haven't overridden any credentials with static values.

AWS SSO Configuration: If you are using AWS Single Sign-On (SSO) credentials, Terraform supports SSO authentication using the aws_sso provider configuration. Make sure you have the correct configuration for the SSO provider.


