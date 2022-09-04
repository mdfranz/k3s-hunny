
# Creating VM's

These examples used bare-metal VM's created by

```
$ uvt-kvm create --disk 20 --memory 4096 --bridge br0 --password ubuntu hpk3sa release=focal
```

# Using it

Assuming you create a host file. 

```
ansible-playbook -k -u ubuntu -i hosts default.yml 
```
