# Back up a local database to s3 using Ansible

### Create a vault file with AWS IAM credentials for Ansible to use:

> ansible-vault create group_vars/all/pass.yml

and include your AWS Key and Secret with permission to create s3 buckets and put objects

> ec2_access_key: [your aws access key ]

> ec2_secret_key: [your aws secret key]

## Install Ansible dependencies

> pip install -r requirements

## Run the backup playbook to backup the database and compress the file

> ansible-playbook s3.yml --ask-vault-pass

## Run the s3 playbook to create an s3 bucket and upload the database backup to s3

> ansible-playbook backup.yml