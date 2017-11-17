# Deploy Jenkins

This playbook deploys Jenkins on a target machine defined in the Inventory file under 'jenkins' group. The playbook is built to run against a CentOS / Red Hat / Amazon Linux machine i.e. YUM distributions. The playbook includes the following roles:

  - common
  - jenkins
 
This playbook can be extended to include other roles as well, such as setup jenkins slave etc.

# Purpose of Roles

#### common:
- Set up a CLI banner (MOTD) in the target hosts
- Install few common packages required at each host.

#### jenkins:
- Install Jenkins and its dependencies on the target host.
- Starts and enables jenkins service on the target host.

## Execution

Use the following adhoc command to test connection to the target hosts from the controller node. The command assumes the instances have been created on AWS using the Amazon Linux AMI and has an ec2-user to which the SSH Keys have been added. Please update the user in the following command based on your environment. 

```sh
$ ansible -i hosts jenkins -m ping --user ec2-user --ssh-common-args='-o StrictHostKeyChecking=no'
```

Once the connections are verified, you can execute the Ansible playbook using the following command

```sh
$ ansible-playbook -i hosts playbook.yaml
```

Verify your deployment by connecting to the target hosts from your browser over port 8080. 8080 is the default port used by Jenkins.
