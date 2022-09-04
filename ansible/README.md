
# Creating VM's

These examples used bare-metal VM's created by

```
$ uvt-kvm create --disk 20 --memory 4096 --bridge br0 --password ubuntu hpk3sa release=focal
```

# Deploying

Assuming you create a host file. Check your hosts.

Requires you to set:
- ansible_user

```
ansible all -k  -i hosts -m ansible.builtin.ping
```

Deploy based on what is in `vars.tf`

- install_ks3
- install_acorn 

(mostly idempotent, won't re-install twice) 

```
ansible-playbook -k -u ubuntu -i hosts default.yml 
```

Remove

```
ansible-playbook -k -u ubuntu -i hosts clean.yml
```


