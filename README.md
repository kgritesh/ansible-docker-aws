# Docker For AWS

This is an example `ansible playbook` to deploy **Docker Swarm** on **AWS** using the CloudFormation template provided by the Docker guys. It implements their starter guide on [ Docker For AWS ](https://docs.docker.com/docker-for-aws/)

## Usage

	ansible-playbook -i inventory infra.yml
	
	
## Configuration

For this playbook to work you will need to update following list of variables inside `group_vars/var` file

	
 + **cf_stack**: Name you want to assign to your cloudformation stack
 
 + **aws_region**: AWS Region 
 
 + **aws_security_key**: AWS Security Key that you will use to login
 
 + **cf_template_url**: Cloudformation Template to use. It has a default value, only change it you are using some custom template
 
 + **cf_role_name**: Name of the IAM role used by cloudformation to create the stack 
 
 Following are the configuration required by the CloudFormation Template
 
 
 + **aws_worker_instance_type**: Type of EC2 instances to be used for workers

 + **aws_manager_instance_type**: Type of EC2 instances to be used for managers

 + **worker_size**: Number of workers in your docker swarm

+ **manager_size**: Number of manager in your docker swarm

+ **enable_system_prune**: Enable if you want Docker for AWS to automatically cleanup unused space on your swarm nodes.

+ **enable_cloudwatch_logs**: Enable if you want Docker to send your container logs to CloudWatch. (“yes”, “no”) Defaults to yes.

+ **worker_disk_size**: Size of Workers’ ephemeral storage volume in GiB (20 - 1024).

+ **manager_disk_size**: Size of Managers’ ephemeral storage volume in GiB (20 - 1024).

+ **worker_disk_type**: Worker ephemeral storage volume type (“standard”, “gp2”).

+ **manager_disk_type**: Manager ephemeral storage volume type (“standard”, “gp2”)