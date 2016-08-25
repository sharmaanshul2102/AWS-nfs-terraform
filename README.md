# AWS-nfs-terraform

First create an AWS EC2 ubuntu 14.04 instance, and IAM user with “administrator” and “power user” access (to get the IAM access and secret keys) and install terraform:


    cd /usr/bin/
    sudo wget https://releases.hashicorp.com/terraform/0.7.2/terraform_0.7.2_linux_amd64.zip
    sudo unzip terraform_0.7.2_linux_amd64.zip && sudo rm terraform_0.7.2_linux_amd64.zip
    cd ~

Then clone the git repo:

    #!/bin/bash
    git clone
    cd AWS-nfs-terraform
    #checks that ssh key id_rsa.pub exists
    if [ -z "$(ls ~/.ssh/ -1 | grep id_rsa.pub)" ]; then
    	# makes ssh key if none exists
    	ssh-keygen -f /home/ubuntu/.ssh/id_rsa -t rsa -N ''
    else
    	echo "ssh key already exists"
    fi

Enter your IAM secret key, IAM access key and AWS region into the var.tf file.
After that run terraform:

    terraform plan
    terraform apply
