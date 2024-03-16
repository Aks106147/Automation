**Assignment 1 - Terraform Modules for Azure Resource Provisioning**

This repository contains a collection of Terraform modules tailored for provisioning various resources on Microsoft Azure. The modules are structured hierarchically to enhance reusability, scalability, and maintainability. Below, you'll find comprehensive descriptions of each module along with instructions on how to utilize them effectively.

### Modules Overview:

1. **Resource Group Module (`rgroup-n01569982`):**
   - Creates a single Azure Resource Group.
   - Returns the name of the resource group to the root module.

2. **Network Module (`network-n01569982`):**
   - Sets up a virtual network with a subnet and a corresponding network security group.
   - Enables traffic over ports 22, 3389, 5985, and 80.
   - Provides the names of the virtual network and subnet to the root module.

3. **Common Services Module (`common-n01569982`):**
   - Establishes a log analytics workspace, a recovery services vault, and a standard storage account with LRS redundancy.
   - Supplies the names of these resources to the root module.

4. **Linux Virtual Machines Module (`vmlinux-n01569982`):**
   - Deploys CentOS 8.2 Linux VMs with public IP addresses organized in an availability set.
   - Installs Network Watcher and Azure Monitor extensions.
   - Sends hostnames, domain names, private IP addresses, and public IP addresses of the VMs to the root module.

5. **Windows Virtual Machines Module (`vmwindows-n01569982`):**
   - Instantiates a Windows Server 2016 VM with a public IP address within an availability set.
   - Incorporates the Antimalware extension.
   - Supplies the hostname, domain name, private IP address, and public IP address of the VM to the root module.

6. **Data Disks Module (`datadisk-n01569982`):**
   - Creates and attaches 4 x 10GB disks to the VMs.

7. **Load Balancer Module (`loadbalancer-n01569982`):**
   - Sets up a public-facing basic load balancer with Linux VMs as its backend.
   - Provides the name of the load balancer to the root module.

8. **Database Module (`database-n01569982`):**
   - Provisions an Azure DB for PostgreSQL Single Server instance.
   - Supplies the name of the DB instance to the root module.

### How to Use:

1. **Root Module :**
   - Define all child modules within this root module.
   - Utilize the outputs received from child modules to display on the screen post-deployment.

2. **Child Modules:**
   - Each child module can be employed independently or as part of the root module.
   - Adjust input variables to suit your specific requirements.
   - Import the requisite resources into your Terraform configuration.

### Notes:

- Ensure that appropriate Azure credentials are set up for Terraform to interact seamlessly with Azure services.
- Customize input variables and resource configurations as per your project's needs.
- Execute `terraform init`, `terraform plan`, and `terraform apply` commands within the root module directory to deploy the resources.
