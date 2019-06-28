# splunkviajenkins

The main goal of this repo is to Deploy Splunk (non-cluster) over AWS using Ansible via Jenkins pipeline & then using Jenkinsfile
Pre reqs:
* Choose Ubuntu Image for EC2 instance
* Connect using your key via putty or ssh client
* Update Ubuntu <br>
$ sudo apt-get update -y
* Check Python version, normally its python3, check<br>
$ python3 --version
* Install ansible <br>
$ sudo apt-get install ansible -y
* check ansible version<br>
$ ansible --version<br>
ansible 2.5.1 (in my case)
* setup hosts file with the client node, to install Splunk<br>
./hosts<br>
[allinone]<br>
172.31.85.210 ansible_user=ubuntu<br>
* check passwordless auth to the above user
* if not, generate ssh keys<br>
$ ssh-keygen -t rsa<br>
* generated key i.e. public key needs to be added to the authorized keys, i.e. <br>
$ ssh-copy-id <user>@<client_ip> <br>
or if its same machine, then copy ./.ssh/id_rsa.pub to ./.ssh/authorized_keys<br>
check the connection again, & check ping connection via ansible, i.e. <br>
$ ansible -i hosts  -m ping all<br>
172.31.85.210 | SUCCESS => {<br>
    "changed": false,<br>
    "ping": "pong"<br>
}<br>


 
