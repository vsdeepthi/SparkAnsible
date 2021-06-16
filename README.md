# Spark-ansible
- Installs Spark cluster with ansible on RHEL 7

## Before Install
- Download spark installable and place it in a folder 
- Ensure a passwordless SSH is setup between all the hosts in the cluster for the {GENERIC_USER}
- Ensure {GENERIC_USER} has permissions to create folders under the path mentioned by varibale {HADOOP_PATH}
- Modify hosts/host with host names of the cluster
- Update vars/var_basic.yml for {DOWNLAOD_PATH}, {PATH_TO_PYTHON_EXE}, {SPARK_HOME}
- Update {PATH_TO_PYTHON_EXE} in ansible.cfg, roles/spark/tasks/main.yml
- Update {MASTER_IP}, {MASTER_HOSTNAME} in vars/var_master.yml, vars/var_workers.yml
- Update {GENERIC_USER}, {GENERIC_USER_GROUP} in vars/user.yml
- Update {PATH_TO_HOSTS} in ansible.cfg to point to the directory that has hosts inventory file

## Install Spark

1. Download Spark to any path
2. Update the {{ download_path }}  in vars/var_basic.yml


### Install Master

run shell like

```
ansible-playbook -i hosts/host master.yml
```

### Install Workers


run shell like:
```


ansible-playbook -i hosts/host workers.yml 

```

