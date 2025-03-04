# terraform-aws
Terraform AWS Cloud examples for beginners

## Terraform Init With s3 Backend

terraform init \
    -backend-config="key=dev/vpc.tfstate" \
    -backend-config="bucket=dcube-terraform-state" \
    -backend-config="region=us-west-2" \
    -backend-config="dynamodb_table=terraform-state-lock"

terraform destroy \
    -backend-config="key=dev/vpc.tfstate" \
    -backend-config="bucket=dcube-terraform-state" \
    -backend-config="region=us-west-2" \
    -backend-config="dynamodb_table=terraform-state-lock"

## RDS DB

cd into environments/dev/rds directory and run the following commands:

terraform init

terraform plan -var-file=../../../vars/dev/rds.tfvars

terraform apply -var-file=../../../vars/dev/rds.tfvars

terraform destroy -var-file=../../../vars/dev/rds.tfvars

## Command Reference

Update all outputs:

<pre>terraform refresh</pre>

Show all outputs:

<pre>terraform show</pre>



