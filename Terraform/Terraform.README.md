Activity : A simple architecture to be scripted in Terraform
1. Create VPC
2. Create Subnet 
3. Create VM
4. Create Firewall rules & routes.
5. 1,2,3,4 using cloud foundation toolkit

Steps performed:

1.Create service account(pratik-service-account) 
2.Create SSH key (JSON file)
3.save the JSON file in the same folder where all .tf files are located.
3.Create three files
    1.variables.tf : file is used to define the variables type and optionally set a default value
    2.terraform.tfvars : file is used to set the actual values of the variables.
    3.main.tf :file contains set of configuration 
4.Fire the commands
    1.terraform init : used to initialize a working directory containing Terraform configuration files. 
    2.terraform plan :  used to create an execution plan.
    3.terraform apply :  used to apply the changes required to reach the desired state of the configuration.
    4.terraform destroy : Infrastructure managed by Terraform will be destroyed.
  
