ec2-ansible


An ansible playbook to deploy EC2 instance

run the following commands:

#sudo apt-get update
#sudo apt install ansible
#ansible-vault create pass.yml

add access and secret keys from amazon in the pass.yml:

{ "ec2_access_key": "Your key",
"ec2_secret_key": "Your key"
}

add the next ip in the hosts file:

[localhost]
127.0.0.1

add this lines in ansible.cfg:

[defaults]
host_key_checking = false
remote_user = ubuntu
private_key_file = "pem file key path"
roles_path = "roles file path"

run the playbook with the next command:
#ansible-playbook "playbook.yml" --ask-vault

**don't forget to change:( in the playbook.yml - (instance creation section")
key_name: " pem file name "
subnet: " your aws subnet"