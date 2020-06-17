#  Ansible script to boot up a Kubernetes cluster
Prerequsite:
Install centos and configure 3 VM & Intall ansible at master node.
Openssh-server must be installed and yum update in all server.



ansible control server

fqdn:kubernetes-master.example.com  kubernetes-master
ip:192.168.2.1 

nodes Conf:

fqdn:kubernetes-worker1.example.com kubernetes-worker1
ip:192.168.2.2

fqdn:kubernetes-worker2.example.com kubernetes-worker2
ip:192.168.2.3 


Configure ssh password less authentication from master to all node.



Add following line to all node /etc/hosts.

192.168.2.1 kubernetes-master.example.com kubernetes-master

192.168.2.2 kubernetes-worker1.example.com kubernetes-worker1

192.168.2.3 kubernetes-worker2.example.com kubernetes-worker2



How to use this (Setup Instructions):

1. Internet connection must be enabled in all nodes.
2. Clone this repository into your master node.
   
   git clone 
   
   After cloned, get into the directory
   
   cd Ans001/centos

3. There is a file "hosts" available in "centos" directory, add your all node ip and fqdn. 

4. Provide your server details in "env_variables" available in "centos" directory.

   
5. Run "settingup_kubernetes_cluster.yml" playbook to setup all nodes and kubernetes master configuration.

   ansible-playbook settingup_kubernetes_cluster.yml
   
6. Run "join_kubernetes_workers_nodes.yml" playbook to join the worker nodes with kubernetes master.

      ansible-playbook join_kubernetes_workers_nodes.yml

7. Verify the configuration from master node.

      kubectl get nodes
	  
	  

File roles:

ansible.cfg - Ansible configuration file created locally.   

hosts - Ansible Inventory File

env_variables - Main environment variable file where specify the master IP and pod network range.

settingup_kubernetes_cluster.yml - Ansible Playbook to check prerequisites, setting up nodes, configure master node.

configure_worker_nodes.yml - Ansible Playbook to join worker nodes with the master node.


playbooks - Its a directory holds all playbooks.    


