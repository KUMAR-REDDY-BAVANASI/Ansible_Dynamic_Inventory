Ansible Dynamic Inventory
============================
Pre-requisites:
1. Ansible Server 

Setup
=========
To get help on dynamic inventory please follow Ansible Official Document

1. Download ec2.py and ec2.ini files

2. Create IAM Programmatic access user with EC2 full access on AWS console

    IAM --> users --> Add user
    Role --> Ec2FullAccess --> Attach to Ansibe Server

3. Export IAM user credentials on Ansible server.

	export AWS_ACCESS_KEY_ID='1bc123'
	export AWS_SECRET_ACCESS_KEY='abc123'

4. add executing permissions to ec2.py script

   chmod 755 ec2.py

5. test the script

   ./ec2.py --list

6. List out servers which are running on ap-south-1a AZ

   ansible -i ec2.py  ap-south-1 --list-hosts
