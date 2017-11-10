# Initial Setup

This playbook configures your AWS account for first time use. This provisions the following resources:

  - VPC
  - Public and Private Subnets
  - Internet Gateway
  - NAT Gateway
  - Security Group

### Expected Variables

The playbook calls a setup role which expects the following variables:

  - vpc_name
  - vpc_cidr_block
  - vpc_region
  - public_subnet_cidr
  - private_subnet_cidr
 
These variables are defined in roles/setup/vars/main.yaml. These can be modified as per the user requirement.

### Dependencies

The following dependencies are required on the controller machine from where the Ansible playbook will be executed. These are basically required by the Ansible Modules which are used in the playbook for creating resources on AWS.

  - python-boto3
  - python-boto
  - python-datautil
  - datautils

Also, AWS cli has to be installed and configured so that the ansible playbook can authenticate to AWS and create resources. Use the following command to configure your awscli

```sh
$ aws configure
```

### Execute Playbook

Once awscli is configured, you can execute the ansible playbook by executing the following command

```sh
$ ansible-playbook playbook.yaml
```

