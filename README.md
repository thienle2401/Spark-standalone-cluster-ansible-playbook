# Ansible Playbook for Apache Spark Standalone
This Ansible playbook setup up a standalone Apache Spark cluster with Hadoop of specified versions. This playbook should work on any standard cloud environment, but OpenStack was used for testing and as main environment for this playbook. 

# Example
1. Update the inventory-file (host) with IP addresses of the instances for the cluster. Ideally, the instance should be clean from an Ubuntu image, and this playbook will install nessessary dependencies. 

2. Check and modify the the version of Apache Spark and Apache Hadoop is required.

3. For this example, we are going to supply the ssh private-key in the command explicityly. Depending on your absible controller, you may not need to supply the private key. However, we need to ensure that the controller host will be able to ssh and has 'root' permission to the remote hosts as defined in the inventory file. 

Execute the command to setup the cluster:

```bash
./ansible-playbook -i host main.yml --private-key [your-key.pem]
```

At the very end, if everything went well, you should see the messages of successfully started master and workers of the cluster. 
