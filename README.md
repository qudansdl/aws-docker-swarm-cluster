# aws-docker-swarm-cluster

## Templates and Playbooks

### Terraform

* `variables.tf`
>Includes environment specific configuration
* `provider.tf`
>Configure AWS as a terraform provider
* `security_groups.tf`
>Allows all inbound/outbound traffic
* `resources.tf`
>Configure EC2 instances
* `install-docker.sh`
>Script to install the latest docker version
* `outputs.tf`
>Declare output values of terraform

### Ansible
* hosts
>Connections for ansible playbook, EC2 instances that ansible operates on
* `playbook.yml`
>Ansible playbook to transform to swarm cluster

## Setup

* Add public ips of EC2 instances to the hosts file
* Export AWS environment variables
```
$ export AWS\_ACCESS\_KEY\_ID="YOUR AWS ACCESS KEY ID"
$ export AWS\_SECRET\_ACCESS\_KEY="YOUR AWS SECRET ACCESS KEY"
```
* Run Terraform and Ansible
```
$ terraform apply
$ ansible -i hosts playbook.yml
```