# splunkviajenkins

The main goal of this repo is to Deploy Splunk (non-cluster) over AWS using Ansible via Jenkins pipeline & then using Jenkinsfile
Pre reqs:
* Choose Ubuntu Image for EC2 instance
* Connect using your key via putty or ssh client
* Update Ubuntu 
$ sudo apt-get update -y
* Check Python version, normally its python3, check
$ python3 --version
* Install ansible 
$ sudo apt-get install ansible -y
* check ansible version
$ ansible --version
ansible 2.5.1 (in my case)
* setup hosts file with the client node, to install Splunk
./hosts
[allinone]
172.31.85.210 ansible_user=ubuntu
* check passwordless auth to the above user
* if not, generate ssh keys
$ ssh-keygen -t rsa
* generated key i.e. public key needs to be added to the authorized keys, i.e. 
$ ssh-copy-id <user>@<client_ip> 
or if its same machine, then copy ./.ssh/id_rsa.pub to ./.ssh/authorized_keys
check the connection again, & check ping connection via ansible, i.e. 
$ ansible -i hosts  -m ping all
172.31.85.210 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}


 
